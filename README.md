# The-Quiz-project-by-hard-coding-variables-keyboard-input
#hard-coding variables keyboard input
def display_question(question, options):
    print(question)
    for i, option in enumerate(options, start=1):
        print(f"{i}. {option}")

def get_user_answer():
    while True:
        try:
            answer = int(input("Enter the number of your answer: "))
            return answer
        except ValueError:
            print("Please enter a valid number.")

def check_answer(user_answer, correct_answer):
    return user_answer == correct_answer

def main():
    # Hard-coded questions, options, and correct answers
    questions = [
        {
            "question": "What is the capital of France?",
            "options": ["Berlin", "Madrid", "Paris", "Rome"],
            "correct_answer": 3  # Paris is the 3rd option
        },
        {
            "question": "What is 2 + 2?",
            "options": ["3", "4", "5", "6"],
            "correct_answer": 2  # 4 is the 2nd option
        },
        {
            "question": "What is the largest planet in our solar system?",
            "options": ["Earth", "Mars", "Jupiter", "Saturn"],
            "correct_answer": 3  # Jupiter is the 3rd option
        },
        {
            "question": "What is the chemical symbol for water?",
            "options": ["H2O", "O2", "CO2", "NaCl"],
            "correct_answer": 1  # H2O is the 1st option
        }
    ]

    score = 0

    print("Welcome to the Quiz App!")
    print("-------------------------")

    for q in questions:
        display_question(q["question"], q["options"])
        user_answer = get_user_answer()

        if check_answer(user_answer, q["correct_answer"]):
            print("Correct!\n")
            score += 1
        else:
            print(f"Wrong! The correct answer was: {q['options'][q['correct_answer'] - 1]}\n")

    print(f"Your final score is: {score}/{len(questions)}")
    print("Thank you for playing!")

if __name__ == "__main__":
    main()
