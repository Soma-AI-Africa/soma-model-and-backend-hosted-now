# Scholarship Recommendation System

[![GitHub license](https://img.shields.io/github/license/Talent5/somaai-model)](https://github.com/Talent5/somaai-model/blob/main/LICENSE) 
[![Build Status](https://travis-ci.org/your-username/your-repo-name.svg?branch=master)](https://travis-ci.org/your-username/your-repo-name) 

This repository contains the code for a Scholarship Recommendation System built with Python, Flask, Scikit-learn, and Firebase. The system leverages machine learning to provide personalized scholarship recommendations to students based on their profiles and preferences.

## Features

- **User Profile Management:** Allows students to create and manage their profiles, including information about their academic background, interests, and financial needs.
- **Scholarship Data Processing:** Efficiently loads, cleans, and preprocesses scholarship data from various sources (e.g., CSV files, databases).
- **Machine Learning-Based Recommendation:** Utilizes advanced machine learning algorithms (TF-IDF, SVD, K-Means Clustering, Cosine Similarity) to generate personalized scholarship recommendations.
- **Deadline Awareness:** Incorporates scholarship deadlines into the recommendation process, prioritizing opportunities with upcoming deadlines.
- **Diversity Promotion:** Recommends scholarships from different categories and clusters to ensure a diverse range of options.
- **RESTful API:** Exposes a Flask-based API to integrate the recommendation engine with other applications or websites.
- **Firebase Integration:** Uses Firebase for user authentication, data storage (Firestore), and potentially background task management.

## Getting Started

### Prerequisites

- Python 3.7+
- Virtual environment (recommended)
- Firebase project (with Firestore and Authentication enabled)
- [Other necessary libraries - list them in `requirements.txt`](requirements.txt)

### Installation

1. Clone the repository:
bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   
2. Create and activate a virtual environment (recommended):
bash
   python3 -m venv env
   source env/bin/activate
   
3. Install dependencies:
bash
   pip install -r requirements.txt
   
4. Set up Firebase credentials:
    - Create a Firebase project and enable Firestore and Authentication.
    - Download your Firebase service account credentials (JSON file).
    - Set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to the path of your JSON file. You can do this temporarily in your terminal:
bash
      export GOOGLE_APPLICATION_CREDENTIALS="/path/to/your/credentials.json"
      
### Configuration

1. **`config.py` (or Environment Variables):**
   - Update the configuration file or set environment variables for:
     - Database settings (Firestore)
     - Scholarship data file path
     - Model directory
     - Any other relevant parameters.

### Running the Application

1. **Start the Flask development server:**
bash
   python app.py 
   
2. **Access the API:**  
   - The API will be accessible at `http://localhost:5000/` (or the port you specified).
   - Use a tool like `curl`, Postman, or a web browser to test API endpoints.

## API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET |  Home route to check if the API is running. |
| `/users` | GET |  Fetches all users. |
| `/user/<user_id>` | GET |  Fetches a specific user by ID. |
| `/login` | POST | Handles user login (replace with secure authentication in production). |
| `/recommendations/all` | GET |  Fetches recommendations for all users. |
| `/recommendations/<user_id>` | GET |  Fetches recommendations for a specific user by ID. |

## Data Format

- **Scholarship Data:**  
   - The scholarship data should be in CSV format with the following columns: (Adjust these according to your actual data)
     - `title`: Title of the scholarship
     - `deadline`: Application deadline
     - `field_of_study`: Field of study (e.g., Computer Science, Engineering)
     - `location`: Location of the scholarship (e.g., Country, State)
     - `university` (optional): University offering the scholarship
     - `amount`: Scholarship amount or benefits
     - `Eligibility`: Eligibility criteria 
     - `application_link`: Link to the application page
     - `Description`: Description of the scholarship
     - `About`: More information about the scholarship provider (optional)
     - `Applicable_programmes`: Applicable degree programs (e.g., Bachelor's, Master's)
     - `application_process`: Description of the application process (optional)
   
- **User Profile Data:** 
   - Stored in Firestore under the `users` collection.
   - Example User Document Structure:
json
     {
       "userId": "unique_user_id",
       "firstName": "John",
       "lastName": "Doe",
       "email": "john.doe@example.com",
       "intendedFieldOfStudy": "Computer Science",
       "preferredLocation": "United States",
       "educationLevel": "Bachelor's Degree",
       // ... other profile fields ... 
     }
     
## Future Work

- Implement a more secure and robust authentication system (JWT, OAuth).
- Integrate a task queue (e.g., Celery) for background processing of recommendations. 
- Explore more advanced recommendation algorithms and fine-tune model parameters.
- Add a user interface for profile creation, browsing scholarships, and viewing recommendations.
- Implement A/B testing for different recommendation strategies.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request to contribute to the project.

## License

This project is licensed under the [MIT License](LICENSE).


**Remember to:**

- Replace the placeholders (e.g., your-username, your-repo-name, specific data fields) with your actual information. 
- Update the requirements.txt file with the correct dependencies for your project.
- Consider adding badges for your CI/CD pipeline, code coverage, or other relevant metrics to enhance your README.
- Provide clear and concise instructions to help others understand and use your project effectively. 
