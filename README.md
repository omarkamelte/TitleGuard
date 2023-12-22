# <p align="center">بسم الله الرحمن الرحيم</p>
# <p align="center">صلى على محمد رسول الله</p>


# TitleGuard
"TitleGuard" simplifies academic title validation. Utilizing Google Forms and Sheets, it seamlessly checks proposed titles for similarity in both Arabic and English. An efficient, cost-free solution for researchers with a user-friendly interface.

The Challenge:
In the academic realm, a researcher endeavors to propose a title for the degree they are pursuing. However, it is imperative for the researcher to distinguish their proposed title from those that are already registered or completed.

The Solution:
To address this challenge, a solution has been devised without necessitating modifications to the college portal. The only modification made is the addition of an extra link in the service menu.

The chosen solution leverages Google tools, which offer a suite of interconnected utilities and scripting capabilities. This approach is both fully functional and accessible at no cost. The implementation involves providing a link to an external Google Form. This form serves as a repository for research information and proposed titles. Upon submission, it initiates an email response to the researcher, incorporating a similarity check with existing titles, both in Arabic and English.

On the backend, the form is linked to a Google Sheet that captures the responses. This sheet is connected to a script featuring a function named 'onFormSubmit,' triggered automatically upon form submission. This function constructs an email using the inserted information and conducts a search for similarity against a predefined list of titles stored in another Google Sheet labeled 'all Titles.' Notably, this sheet also acts as the response destination for another Google Form designed to accept new titles. This ensures a consistent update of existing titles, maintaining a comprehensive record.

Upon receiving the email, the researcher can make informed decisions, either proceeding with the proposed title or exploring alternative options. The relevant script and supporting methods can be found in the mentioned repository, contributing to the fulfillment of the primary request."

### TitleGuard Script

#### Overview:

The `onFormSubmit` function is triggered by a Google Form submission. It extracts submitted titles and user information, then checks the similarity of the titles against existing titles in both Arabic and English. The results are emailed to the researcher.

#### Functions:

1. **onFormSubmit(e):**
   - Triggers on form submission.
   - Retrieves submitted data and calculates title similarity.
   - Composes an email with the results and sends it to the researcher.

2. **calculateSimilarities(submittedText, titles, arabic=false):**
   - Calculates similarity scores for each title.
   - Filters and sorts results based on similarity percentage and title length.
   - Returns a formatted table of similarities.

3. **calculateSimilarity(textA, textB):**
   - Calculates the percentage similarity between two strings.

4. **simi(str1, str2, LevenshteinDistance):**
   - Compares two strings for similarity.
   - Returns a value between 0 and 100 representing the percentage of similarity.

5. **Wsimi(w1, w2, lev):**
   - Checks if two words are exactly equal or have Levenshtein distance less than or equal to 2.

6. **LevenshteinDistance(s1, s2):**
   - Calculates the Levenshtein distance between two strings.

#### Usage:

1. The `onFormSubmit` function is triggered automatically upon Google Form submission.
2. Results are emailed to the researcher, displaying the similarity percentages in a formatted table.
3. Researchers can decide whether to proceed with the proposed title or choose another.

#### Note:

- Replace `'ADD YOUR SPREADSHEET ID'` with the actual ID of the spreadsheet containing titles.

#### Powered by: Omar Kamel, MSc
