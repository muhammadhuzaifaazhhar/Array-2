# Array-2
def display_names_and_scores(names, scores):
    for i in range(len(names)):
        print(f"{names[i]} - Exam Score: {scores[i]}")

def display_highest_and_lowest(names, scores):
    high_var = 0
    low_var = 999
    high_index = low_index = 0

    for i in range(len(scores)):
        if scores[i] > high_var:
            high_var = scores[i]
            high_index = i
        if scores[i] < low_var:
            low_var = scores[i]
            low_index = i

    print(f"Highest Score: {names[high_index]} - Exam Score: {high_var}")
    print(f"Lowest Score: {names[low_index]} - Exam Score: {low_var}")

def read_data_from_file(file_path):
    names = []
    scores = []
    with open(file_path, 'r') as file:
        for line in file:
            data = line.strip().split(',')
            names.append(data[0])
            scores.append(int(data[1]))
    return names, scores

# Read data from a file (assuming the file has format: lastname,score)
file_path = 'student_scores.txt'
last_names, exam_scores = read_data_from_file(file_path)

# Display names and scores
print("Names and Exam Scores:")
display_names_and_scores(last_names, exam_scores)

# Display highest and lowest scores
print("\nHighest and Lowest Scores:")
display_highest_and_lowest(last_names, exam_scores)
