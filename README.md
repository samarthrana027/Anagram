# Anagram Checker

A simple and interactive web application built with Streamlit to check if two strings are anagrams of each other.

## Features

- **User-friendly Interface**: Clean and intuitive design powered by Streamlit
- **Real-time Validation**: Check if two strings are anagrams instantly
- **Case-insensitive Comparison**: Automatically converts inputs to lowercase for accurate results
- **Color-coded Results**: 
  - 🟢 Green text for "Anagram"
  - 🔴 Red text for "Not Anagram"
- **Session State Management**: Maintains results across interactions

## What is an Anagram?

An anagram is a word or phrase formed by rearranging the letters of another word or phrase, using all the original letters exactly once.

**Examples:**
- "listen" and "silent" are anagrams
- "evil" and "vile" are anagrams
- "python" and "typhon" are anagrams

## Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package installer)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/samarthrana027/Anagram.git
cd Anagram
```

2. Install required dependencies:
```bash
pip install streamlit
```

## Usage

Run the Streamlit application:
```bash
streamlit run streamlit_pro_anagram.py
```

The app will open in your default web browser at `http://localhost:8501`

### How to Use

1. Enter the **first string** in the text input field
2. Enter the **second string** in the text input field
3. Click the **"Check for Anagram"** button
4. View the result displayed in color-coded text:
   - Green = Anagram found
   - Red = Not an anagram

## Project Structure

```
Anagram/
├── streamlit_pro_anagram.py    # Main application file
└── README.md                    # Project documentation
```

## How It Works

The application uses a simple but effective algorithm:

1. **CheckAnagram()**: Compares sorted characters of both strings
   - Converts both strings to lowercase
   - Sorts all characters in each string
   - Compares if sorted results are identical

2. **validateAnagram()**: Handles the validation logic
   - Retrieves input from session state
   - Calls CheckAnagram() function
   - Updates session state with result and color

## Code Explanation

### Main Functions

- **`CheckAnagram(str1, str2)`**: Core logic that checks if two strings are anagrams
  - Returns "Anagram" if strings contain same characters
  - Returns "Not Anagram" otherwise

- **`validateAnagram()`**: Processes user input and manages results
  - Gets strings from Streamlit session state
  - Converts to lowercase for case-insensitive comparison
  - Sets result color and text for display

## Technologies Used

- **Python 3**: Programming language
- **Streamlit**: Web application framework for building interactive apps
- **HTML/CSS**: For styling the results display

## Example Usage

```
Input 1: Listen
Input 2: Silent
Output: Anagram (displayed in green)

Input 1: Hello
Input 2: World
Output: Not Anagram (displayed in red)
```

## Limitations

- Spaces and special characters are included in the comparison
- Currently optimized for English language strings
- No dictionary validation - purely character-based comparison

## Future Enhancements

- Add support for multiple language anagrams
- Ignore spaces and punctuation in comparison
- Add a list of common anagram examples
- Word dictionary validation
- Export results to file

## Author

**Samarth Rana** - [GitHub Profile](https://github.com/samarthrana027)

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a new branch for your feature
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## Support

If you encounter any issues or have suggestions for improvement, please open an issue on the GitHub repository.

---

**Happy Anagram Checking!** 🎉
