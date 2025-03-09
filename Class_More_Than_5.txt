import pandas as pd

def find_classes(courses: pd.DataFrame) -> pd.DataFrame:
    df = courses.groupby('class')['student'].nunique().reset_index(name = 'cnt')
    df = df[df['cnt']>=5]
    return df[['class']]