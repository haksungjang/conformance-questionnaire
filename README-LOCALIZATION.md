# Localizing the OpenChain Conformance Questionnaire

## Workflow
* The default language representation of the questionnaire is maintained in the file questionnaire.json in the master branch
* The conformance team will update the questionnaire up until a release
* The questionnaire is reviewed by the conformance team and "released"
* A new branch is created for the release containing only the file questionnaire.json
* Localized versions of the file questionnaire.json are created using the naming convention questionnaire_LANGTAG.json where LANGTAG specifies the language in the [RFC 5646 format](https://tools.ietf.org/html/rfc5646) (e.g. questionnaire_en.json)
* The localized versions are reviewed and a full release is determined
* The branch is tagged for release
* The files are uploaded to the conformance web application making it available to the users
* Incremental changes impacting a single language file can be made within the branch and uploaded as an individual file
* Changes that impact all files should create a new version of the questionnaire on a new branch

## Specification Version Consistency
All of the `"specVersion"` fields in the questionnaire.json files must have exactly the same value.

## Specifying the language in the JSON file
The `"language"` field in the JSON file must match the [RFC 5646 format](https://tools.ietf.org/html/rfc5646) language tag indicated the questionnaire file name.

## Fields requiring localization
The following fields are used in generating the PDF document and should be localized:
* `"title"`: The title Questionnaire to be used in the PDF document.
* `"contextText"`: The text to be used at the beginning of the Context section in the PDF document (preceeds the preambleText).
* `"questionsText"`: The text to be used at the beginning of Questions section in the PDF document.
* `"completedText"`: Column heading for checkboxes on whether the question was completed
* `"statusText"`: Column heading for the status on a particular question response
* `"answerColumnText"`: Column heading for the answer to the question
* ` "tocText"`: The text to be used at the beginning of the Table of Contents in the PDF document.
* `"preambleText"`: Text used to describe the questionnaire.  This text precedes the questionnaire text in the PDF document.

The following section fields in the questionnaire file should be localized:
* `"title"`: The title of the section to be displayed in the UI
* `"questions"`: The list of questions belonging to the section

The following question fields in the questionnaire file should be localized:
* `"question"`: Text for the question.  Must be UTF-8 encoded.
* `"notApplicablePrompt"`: Optional prompt to display for not applicable
* `"evidencePrompt"`: Reserved for future use as a prompt to the user when additional information is requested for a question
* `"evidenceValidation"`: Reserved for future use as a regular expression validation to be applied against the response to the evidence request

NO other fields in the questionnaire.json file should be localized.
