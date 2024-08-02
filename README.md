# ATS-Checker
A simple package that performs standard ATS checking using specified job requirements. This package extracts relevant information from a PDF resume, compares it against the job requirements provided in JSON format, and generates an ATS report with a matching score.


To install the ATS Checker package, you can use the following command:

bash

Copy code

`pip install ats_checker` 

## Usage

### Importing and Using the `load_resume` Function

The `load_resume` function takes the path to a PDF resume file and a dictionary of job requirements. It returns a dictionary with the extracted information and a summary of the ATS match.

### Example

1.  **Create Job Requirements in JSON Format**:

json

Copy code

`{
    "title": "Software Developer",
    "skills": ["Python", "Django", "JavaScript", "React", "SQL"],
    "experience_years": 3
}` 

2.  **Python Script to Use the Package**:

python

Copy code

`# main.py
import json
from ats_checker import load_resume

# Load job requirements
job_requirements = {
    "title": "Software Developer",
    "skills": ["Python", "Django", "JavaScript", "React", "SQL"],
    "experience_years": 3
}

# Path to the PDF resume file
resume_path = 'path_to_resume_file.pdf'

# Load the resume and get the ATS report
ats_report = load_resume(resume_path, job_requirements)

# Print the ATS report
print(json.dumps(ats_report, indent=2))` 

### Output

The `load_resume` function returns a dictionary containing the extracted information and a summary of the ATS match, including the matched skills, skills match percentage, experience match status, and total ATS score.

json

Copy code

`{
  "name": "John Doe",
  "email": "john.doe@example.com",
  "skills": ["Python", "Django", "SQL"],
  "education": ["Bachelor"],
  "experience_years": 4,
  "matched_skills": ["Python", "Django", "SQL"],
  "skills_match_percentage": 60.0,
  "experience_match": true,
  "total_ats_score": 80.0
}` 

## Package Structure

-   `ats_checker/__init__.py`: Initializes the package and imports necessary functions.
-   `ats_checker/parser.py`: Contains functions for extracting information from the resume.
-   `ats_checker/matcher.py`: Contains functions for matching the resume data with job requirements.
-   `ats_checker/report.py`: Contains functions for generating the ATS report and score.

## Installation for Development

If you want to install the package for development, use the following command:

bash

Copy code

`pip install -e .` 

This will install the package in editable mode, allowing you to make changes to the code and use it without reinstalling.

## Contributing

If you would like to contribute to this package, please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License.
