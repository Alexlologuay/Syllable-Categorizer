# MIT License
# 
# Name Syllable Categorizer
# This program categorizes names from a list based on their syllable count.
# Authors: [Lucas Flores, Besay Romero, Babikir and Manuel Alejandro Granda Morales]
# Date: [13/11/2024]

def categorize_names_by_syllable_count(names):
    """
    Categorize names by their syllable count.
    
    Parameters:
    - names (list of str): The list of names to categorize by syllable count.
    
    Returns:
    - dict: A dictionary where keys are syllable counts, and values are lists of names with that count.
    """
    
    # Step 1: Initialize an empty dictionary to store results
    syllable_groups = {}
    
    # Step 2: Define a helper function to estimate syllable count
    def estimate_syllables(name):
        vowels = "aeiou"
        count = sum(1 for char in name.lower() if char in vowels)
        return max(1, count)  # Ensure at least 1 syllable
    
    # Step 3: Iterate over each name in the list
    for name in names:
        # Step 4: Estimate the syllable count of the current name
        syllable_count = estimate_syllables(name)
        
        # Step 5: Check if this syllable count is already a key in the dictionary
        if syllable_count not in syllable_groups:
            # If not, create a new list for this count
            syllable_groups[syllable_count] = []
        
        # Step 6: Append the current name to the list for its syllable count
        syllable_groups[syllable_count].append(name)
    
    # Step 7: Return the completed dictionary
    return syllable_groups

sample_names = ["Besay", "Babikir", "Lucas", "Alejandro"]
# Execute the function with the sample input
result = categorize_names_by_syllable_count(sample_names)

# Print the result to show the output
print(result)
