# Anagram Checker - Project Report

## Project Overview
**Project Name:** Anagram Checker  
**Technology Stack:** Python, Streamlit  
**Purpose:** A web-based application to check if two strings are anagrams of each other

---

## Project Description

The Anagram Checker is a Streamlit-based application that provides a user-friendly interface to validate whether two input strings are anagrams. The application demonstrates fundamental string comparison algorithms and session state management in Streamlit.

### Key Features
- **Simple User Interface**: Clean, centered layout for easy use
- **Two Input Fields**: Accept two strings for comparison
- **Real-time Validation**: Check if strings are anagrams with a single button click
- **Visual Feedback**: Color-coded results (Green for "Anagram", Red for "Not Anagram")
- **Case-Insensitive Matching**: Converts input strings to lowercase before comparison

---

## Technical Architecture

### Components

#### 1. **CheckAnagram Function**
```python
def CheckAnagram(str1, str2):
    if sorted(str1) == sorted(str2):
        return "Anagram"
    else:
        return "Not Anagram"
```
- **Purpose**: Core logic for anagram validation
- **Algorithm**: Sorts characters in both strings and compares them
- **Time Complexity**: O(n log n) due to sorting
- **Space Complexity**: O(n)

#### 2. **validateAnagram Function**
```python
def validateAnagram():
    str1 = st.session_state.string1.lower()
    str2 = st.session_state.string2.lower()
    result = CheckAnagram(str1, str2)
    
    if result == "Anagram":
        st.session_state.result_color = "green"
        st.session_state.result_text = result
    else:
        st.session_state.result_color = "red"
        st.session_state.result_text = result
```
- **Purpose**: Handles validation workflow and session state management
- **Features**:
  - Case normalization (converts to lowercase)
  - Result determination
  - Dynamic color assignment based on result

#### 3. **Streamlit UI Configuration**
- **Page Configuration**: 
  - Title: "Anagram Checker"
  - Layout: Centered
  - Sidebar: Collapsed by default

- **UI Elements**:
  - Two text input fields with keys `string1` and `string2`
  - Check button for validation trigger
  - Conditional result display with HTML styling

---

## Algorithm Analysis

### Anagram Checking Method
**Approach**: Sorting-based comparison

**How it works:**
1. Both strings are sorted alphabetically
2. If sorted strings are identical, they contain the same characters in the same frequency
3. Therefore, they are anagrams of each other

**Example:**
- Input 1: "listen"
- Input 2: "silent"
- Sorted 1: "eilnst"
- Sorted 2: "eilnst"
- Result: ✓ Anagram

### Pros and Cons

**Advantages:**
- Simple and intuitive implementation
- Easy to understand and maintain
- Works for any character type (letters, numbers, special characters)

**Disadvantages:**
- O(n log n) time complexity (not optimal)
- Could be optimized to O(n) using character frequency counting

**Optimal Alternative (Character Count):**
```python
from collections import Counter
def CheckAnagram(str1, str2):
    return Counter(str1) == Counter(str2)
```
- Time Complexity: O(n)
- More efficient for large strings

---

## User Experience Flow

1. **User Input**: User enters two strings in the input fields
2. **Button Click**: User clicks "Check for Anagram" button
3. **Processing**: 
   - Strings are converted to lowercase
   - Comparison algorithm executes
4. **Result Display**: Result appears with color coding
   - Green: Anagram found
   - Red: Not an anagram

---

## State Management

The application uses Streamlit's `session_state` to maintain:
- `string1`: First input string
- `string2`: Second input string
- `result_color`: Display color for result
- `result_text`: Text to display ("Anagram" or "Not Anagram")

This ensures the result persists across user interactions within the session.

---

## Code Quality and Best Practices

### Strengths
✓ Modular function design  
✓ Clear separation of concerns  
✓ Proper use of session state  
✓ Case-insensitive comparison  
✓ HTML styling for better UX  

### Areas for Improvement
- Add input validation (empty string handling)
- Add documentation/docstrings
- Consider whitespace handling
- Add error handling
- Implement more efficient algorithm
- Add unit tests

---

## Potential Enhancements

1. **Input Validation**
   - Check for empty strings
   - Display warning messages for invalid input

2. **Character Handling**
   - Option to ignore whitespace
   - Option to ignore special characters
   - Option to ignore case sensitivity (already implemented)

3. **History Feature**
   - Maintain a log of previous checks
   - Allow users to review past comparisons

4. **Performance Optimization**
   - Use character frequency counting instead of sorting
   - Add benchmarking for large strings

5. **Additional Features**
   - Batch processing for multiple pairs
   - Export results to file
   - API endpoint creation

---

## Installation and Usage

### Prerequisites
- Python 3.7+
- Streamlit

### Installation
```bash
pip install streamlit
```

### Running the Application
```bash
streamlit run streamlit_pro_anagram.py
```

### Usage
1. Open the application in your browser (default: `http://localhost:8501`)
2. Enter first string in "Enter the first string" field
3. Enter second string in "Enter the second string" field
4. Click "Check for Anagram" button
5. View the result with color coding

---

## Testing Scenarios

| String 1 | String 2 | Expected Result | Status |
|----------|----------|-----------------|--------|
| listen | silent | Anagram | ✓ |
| hello | world | Not Anagram | ✓ |
| abc | bca | Anagram | ✓ |
| abc | def | Not Anagram | ✓ |
| LISTEN | silent | Anagram | ✓ |
| (empty) | (empty) | Anagram | ✓ |

---

## Conclusion

The Anagram Checker is a well-structured Streamlit application that effectively demonstrates:
- String manipulation in Python
- Algorithm implementation
- Streamlit framework capabilities
- Session state management
- User interface design

The application is production-ready for basic use cases. Future improvements should focus on input validation, performance optimization, and additional features based on user requirements.

---

## Project Metadata

**Created**: 2026-07-05  
**Repository**: samarthrana027/Anagram  
**Main File**: streamlit_pro_anagram.py  
**License**: Not specified  
**Status**: Active
