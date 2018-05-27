# Survey App
An online poll website

## Users and Authentication
There are two types of users, surveyors and surveyees. 
A surveyor can sign up for a SurveyApe account to be able create and manage surveys.
A surveyee may or may not have an SurveyApe account.  
SurveyApe does distinguish between surveyor and surveyee accounts, i.e., anyone with an account can both create surveys and take surveys.
A user must use a valid email to sign up for a SurveyApe account. 
The signing up UI must allow the user to provide his email and intended password.
The app sends a verification email to the user upon registration with a verification code. The user needs to use that verification code to complete his account registration. A registered user cannot really use features in the app until his account is verified. A confirmation/welcome email must be sent to the user after completion of account verification.
## Survey Types and Question Types
The following survey types are supported. 

General survey: All participants will use the same invitation link to fill-in and submit the survey. Participants can be invited through emails, QR code, and URL. SurveyApe does not attempt to track whether the same person submit multiple surveys or not. An exception to this, however, is that if a user has signed into SurveyApe, he cannot take the same general survey more than once, or it is going to complicate the auto saving feature where  a signed-in user can pick up and resume an unfinished survey, whose progress was automatically saved last time.

Closed invitation-only survey: Each participant is pre-registered by the owner and will have a unique invitation link. A particular invitation link can only be used once: once a user completed a survey through his/her invitation link, this link should be invalided.(This survey can only invited through email)

Open unique survey: everyone can follow a link to register for a survey by either signing into SurveyApe, signing up for a SurveyApe account, or just providing his email. 

For a signed in user, he can take the survey within the app, and submit only once.
For users who provided emails only and do not have SurveyApe accounts, a unique participating link will be sent to his email that he can follow to complete the survey. Each participation link can be used only once, just like in closed surveys.
All surveys are anonymous in that the owner will not be able to see who provides which answer. If a survey has fewer than two participants, it is considered incomplete and its results will not be shown to the owner
 
The following question types are supported
 
Multiple choice questions, which have different subtypes and styles
Choice type

Text only: all choices are given as text.

Image only: every choice is given as an image.

Answer type:

Single selection

multiple selections

Visual style (note: for image questions, it’s OK to support radio buttons and checkboxes)
Dropdownlist (Single selection only)
Radio button (Single selection only)
Checkbox (Single & multiple selection)
Yes/no questions. This can be viewed as a special type of multiple choice questions, where there are only two answers to select: Yes or No.

Short answer questions, where the answer is plain text.

Date/time questions, which allow the surveyee to pick a Date and/or Time as the answer

Star rating questions,  which allow surveyees to rank a variable using 0-5 stars.

## Surveyor

Survey creation

User interface will be provided for a surveyor to create a survey, specify type (optionally register participants), optionally an end time, and enter the questions one by one.
A surveyor may choose to save a survey, and continue to edit it later, or publish a survey when he is done. A survey is not visible to participants until is is published. 
A user may choose to unpublish a published survey, provided that there no submitted results yet. 
If a survey is unpublished, the survey is no longer visible to surveyees, and no surveys can be taken or submitted until published again.
The surveyor can choose to extend the end time of a survey if it has not ended yet. 
The survey automatically closes when its end time has reached. If the end time has not been specified, the surveyor can choose to close a survey at anytime.
Before a survey is closed, the surveyor can add/invite surveyees as allowed by the survey type.
Survey results and stats

The surveyor will be given a view to browse the results of each survey
For a selected survey, the surveyor will be able to see the following general metrics
Start time
End time
of participants
Participation rate (# of submissions / # of invited/ registered surveyees, where applicable).
Metrics for each question
The surveyor will be able to see the results each question
and distribution of each answer choice, when applicable.
All answer text provided by the surveyees, when applicable.
Response rate among total # of submissions.
## Surveyee

Survey participation

Surveyee takes surveys through the web interface. It is NOT required for surveyees to sign into SurveyApe to be able to take any survey. If, however, a surveyee has signed in,  he will be able to make use of features in b, c, and d.
A surveyee is not required to finish a survey within one session, when applicable. He can always sign out, and sign in again later to continue with a survey.

As each answer is selected for any question, it gets saved on the server so that the surveyee’s progress and results do not get lost even if he chooses to take a long time to finish a survey through multiple sessions.
A surveyee can see a list of all the surveys he has taken. For any submitted or expired survey, it is presented in a read-only mode and cannot accept further changes from the surveyee.

Surveyee is sent a confirmation upon submission of a survey, whenever applicable. In the case of General Survey, the email can either be taken from the current user who has signed in, or optionally provided by the user upon submission of the survey; i.e., give the user the option to get a confirmation email upon submission.
For a participant who has currently signed in, the participant info should be automatically filled in when applicable.

## Bonus Feature
Export and import of surveys through JSON
A surveyor can export a survey to text file in JSON format. 
The surveyor is given the option to specify a file name.
Images can be treated as URLs.
There are no specific schema requirements for the JSON file, other than it is in valid JSON format, and straightforward to understand.
When adding questions, a surveyor can import from a JSON file to add multiple questions at a time, appending to the end of current questions. The supported schema for import must be compatible with the export; i.e., importing from a previously exported file will recreate the same set of questions in the same relative order.

