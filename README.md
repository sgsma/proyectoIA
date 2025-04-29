outliers = {}
for col in cols:
    q1 = np.percentile(data[col], 25)
    q3 = np.percentile(data[col], 75)
    iqr = q3 - q1
    lower_bound = q1 - 1.5 * iqr
    upper_bound = q3 + 1.5 * iqr
    outliers[col] = (data[col] > upper_bound).sum() + (data[col] < 
    lower_bound).sum()

    print(f'Outliers in {col}: {outliers[col]}')
