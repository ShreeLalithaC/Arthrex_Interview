# The_Question
Let us assume that Arthrex wants to hire an intern.
The recruiter from Arthrex starts gathering a list of interns from its database.
In order to keep the hiring pipeline healthy, every time a recruiter calls up a candidate 
to schedule an interview, he also asks the candidate to provide a list of his 
classmates.
Write a program in a language of your choice to list all the candidates that could be 
contacted by the above method, until a candidate is hired or the complete list of 
candidates along with their classmates is exhausted.
Note: No candidate should be contacted more than 
once. Use following data for the problem:
Person              Friends
A                   B, C, J
D                   E, F, G
H                   I, K, V
J                   V
K                   L, M, N, A
O                   P, V, U
Q                   S,T, D
U                   H, J
V                   W, X, Y, Z


# Code
def Arthrex_hire(person, D1):
    contacted = set()
    Arthrex_candidates = []
    Next = [person]

    while Next:
        current_person = Next.pop(0)
        if current_person not in contacted:
            Arthrex_candidates.append(current_person)
            contacted.add(current_person)
            if current_person in D1:
                Next.extend(D1[current_person])

    return Arthrex_candidates

def main():
   
    D1 = {
        'A': ['B', 'C', 'J'],
        'D': ['E', 'F', 'G'],
        'H': ['I', 'K', 'V'],
        'J': ['V'],
        'K': ['L', 'M', 'N', 'A'],
        'O': ['P', 'V', 'U'],
        'Q': ['S', 'T', 'D'],     
        'U': ['H', 'J'],
        'V': ['W', 'X', 'Y', 'Z']
    }

   
    selected_candidates = input("Enter the character selected for the job: ")
    candidates_contacted = Arthrex_hire(selected_candidates, D1)
    print("Candidates contacted:", candidates_contacted)

if __name__ == "__main__":
     main()

# Output: Enter the character selected for the job: O
Candidates contacted: ['O', 'P', 'V', 'U', 'W', 'X', 'Y', 'Z', 'H', 'J', 'I', 'K', 'L', 'M', 'N', 'A', 'B', 'C']

   
# Explanation:

-- The 'D1' is used as a variable to store the database of the candidates who are all attending the interview are split into two as 'Person' and 'Friends'.
-- These values are further added together by creating a dictionary with keys and values in it.
-- In order to achieve the output, I have used a define function which returns the respective output.
-- I have Used the 'While' and 'for' loop and the 'if' condition for the range and condition.
-- After checking the conditions, it will return the output only if the condition satisfies.
-- When a new value i.e., the candidate name is given, it will return the output as the question demands and returns the same if it does not meet with the condition. 
-- For example: After entering the character selected for the job 'O', it returns the output as:
Candidates contacted: ['O', 'P', 'V', 'U', 'W', 'X', 'Y', 'Z', 'H', 'J', 'I', 'K', 'L', 'M', 'N', 'A', 'B', 'C']


