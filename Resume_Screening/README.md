Overview
This application uses Streamlit to predict job categories based on uploaded resumes. The model is built using machine learning techniques, where resumes are processed, cleaned, and classified into predefined job categories.

Features
Resume Upload: Users can upload resumes in PDF, DOCX, or TXT format.
Text Extraction: Extracts text from the uploaded resume using appropriate libraries based on the file type.
Text Cleaning: Cleans the extracted text to remove unnecessary characters, URLs, and other non-relevant content.
Job Category Prediction: Utilizes a pre-trained machine learning model to predict the job category from the cleaned resume text.
Category Mapping: Maps predicted category IDs to human-readable job titles.
Libraries Used
streamlit: For creating the web interface.
pickle: For loading pre-trained machine learning models.
re: For regular expression operations to clean text.
nltk: For natural language processing tasks.
pdfminer: For extracting text from PDF files.
docx2txt: For extracting text from DOCX files.
Installation
Ensure you have the required libraries installed. You can install them using pip:

bash
Copy code
pip install streamlit pickle5 nltk pdfminer.six docx2txt
Usage
Run the Application: Execute the script using Python to start the Streamlit app.
bash
Copy code
streamlit run <your_script_name>.py
Upload Resume: Use the file uploader to select and upload a resume file in PDF, DOCX, or TXT format.

View Prediction: The application will display the predicted job category based on the resume content.

Code Breakdown
clean_resume(resume_text: str) -> str: Function to clean the resume text by removing URLs, hashtags, mentions, special characters, and non-ASCII characters.
main(): Main function to run the Streamlit app. It handles file uploads, text extraction, cleaning, prediction, and displays the result.
Code Title
"Resume Job Category Prediction System"
