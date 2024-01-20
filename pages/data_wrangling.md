# Data Wrangling

<font size='4'>
A high quality dataset was created from a subset of the CTN0027 public dataset.  From the public dataset, we consumed the following tables:<br>
<br>

![Data Wrangling Proces](/images/sn1.png) <br>
<br>

<p>
    <img src="images/Slide1.png" alt="Opioid Crisis in America" width="700" height="360" style="middle">
</p>



## Flatten Dataframes
This is a custom function that encodes the week of treatment into each clinical datapoint.

```Python
def flatten_dataframe(df,start,stop,step):
    """
    Flattens a dataframe by creating separate dataframes for each week of clinical data,
    renaming columns with the corresponding week number, and merging all dataframes into one,
    reshaping dataframe to 1 row per patient, with all clinical data properly encoded into columns.

    Args:
        df (pandas.DataFrame): The input dataframe.
        start (int): The starting week number.
        stop (int): The stopping week number.
        step (int): The step size between weeks.

    Returns:
        pandas.DataFrame: The flattened dataframe.

    """
    # create a new dataframe for every week of clinical data
    # the name of the dataframe will be VISIT+number of visit
    for i in range(start,stop+1,step):
        globals()['VISIT%s' % i] = df[df['VISIT']==i]

    # for each dataframe beteween start and stop
    # add the value in VISIT to the end of the name of each column +"_"+"visit"
    for i in range(start,stop+1,step):
        for col in globals()['VISIT%s' % i].columns:
            if col != 'patdeid':
                globals()['VISIT%s' % i][col+'_'+str(i)] = globals()['VISIT%s' % i][col]
                # after columns are annoted, drop original columns            
                globals()['VISIT%s' % i] = globals()['VISIT%s' % i].drop(columns=col)
            else:
                pass

    # merge all dfs using left merge on patdeid
    for i in range(start,stop+1,step):
        if i == start:
            df = pd.merge(globals()['VISIT%s' % i], globals()['VISIT%s' % (i+step)], on='patdeid', how='left')
        elif i < stop:
            df = pd.merge(df, globals()['VISIT%s' % (i+step)], on='patdeid', how='left')
        else:
            pass

            # drop erroneous visit columns, as the visit is encoded in each column
            df = df.drop(columns=[col for col in df.columns if col.startswith('VISIT')], axis=1)
            

            return df
```
## Merge Dataframes
- This function will merge a group of dataframes with common keys
- The dataframes must be stored on a list and will be treated as one iterable
```Python
# create function to merge dataframes using functools reduce
def merge_dfs(dfs):
    """
    Merge the given list of DataFrames into one DataFrame.

    Parameters:
    dfs (list): A list of DataFrames to be merged.

    Returns:
    pandas.DataFrame: The merged DataFrame.
    """
    from functools import reduce
    df = reduce(lambda left,right: pd.merge(left,right,on='patdeid'), dfs)
    return df
```
</font>

## Data Dictionary

## Data Aggregation Process