import pandas as pd

file_path = 'GradeDistributionGitHub/2023Spring.csv'
data = pd.read_csv(file_path)

def find_matching_rows(input_value):
    input_value_lower = input_value.lower()
    matching_rows = data[data['Course Name'].str.lower() == input_value_lower]
    return matching_rows

user_input = input("Enter the value to search in 'Course Name' column: ")

matching_rows = find_matching_rows(user_input)


if not matching_rows.empty:
    matching_rows['Percentage'] = (matching_rows.iloc[:, 5] / matching_rows.iloc[:, 22]) * 100
    print("\n\n\n")
    print("Here's all the professors that taught Calc 1 in Spring 2023")
    print("\n\n\n")

    sorted_rows = matching_rows.sort_values(by='Percentage', ascending=False)
    
    for index, row in sorted_rows.iterrows():
        percentage = row['Percentage']
        print(f"A's Given: {percentage:.2f}%")
        desired_columns = row.iloc[[21]]
        print(desired_columns.to_string(header=False))  
        print() 
else:
    print(f"No matching value found for '{user_input}' in 'CRS TITLE' column.")
print("\n\n\n")
