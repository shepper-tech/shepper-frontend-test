# :pencil: Shepper Front-End Developer Test

## :book: Background
<img align="right" width="220" src="https://github.com/shepper-tech/shepper-frontend-test/blob/master/app_preview.png?raw=true">

Shepper performs inspections on properties and assets for a wide variety of businesses ranging from property condition checks to customer experience checks and retail audits, all carried out by our gig economy workers (called Shepherds) through filling out a checklist of questions via our mobile app.
  
Each company and inspection has different requirements in terms of what types of data need to be collected about the property or asset being inspected. We create checklists of questions designed to capture this data from the Shepherd carrying out the inspection.
  
As an example, the checklist for a rental property being inspected before guests arrive may contain an “input” question such as “Describe the condition of the kitchen” with a text input field and a “boolean” question like “Is the WiFi working?” which would offer a two-choice single selection. You can see how this checklist would appear in the app for the Shepherd on the right. 👉 

## :trophy: Challenge
We would like you to build a simple React app customers could use to create and save their inspection checklists.

Checklists are made up of sections, and each section contains one or more questions. Users should be able to add sections, set a title, and remove existing sections. Within each section a user can add questions which will be a certain “question type.” There could be many different question types but for this test we will only be implementing the “boolean” and “input” question types, which will be returned from a [mocked API response](https://github.com/shepper-tech/shepper-frontend-test/blob/master/question_types_response.json).

- **Boolean Question Type:** Boolean questions are questions which have two possible answers, and only one can be selected during the inspection. The checklist builder should allow the user to enter the question title and then enter two possible answers to be shown within the app.

- **Input Question Type:** Input questions are intended to capture some string-based input from the Shepherd during the inspection. The checklist builder should allow the user to enter the question title and then enter a maximum character limit for the input field displayed in the app.

Users should be able to edit, re-order or delete the questions within a section. A user should also be able to cancel editing a question and any changes should not be applied.

A checklist may only be saved if it has at least one section containing one question within it.

Finally, the “Save” button should display the JSON representing the checklist that would have been sent to the API in a real-world situation. Actually making API requests is outside of the scope of the test.

### Example Output
Below is an example of the expected format of the JSON output from the checklist builder. You can also refer to the included [JSON Schema](https://github.com/shepper-tech/shepper-frontend-test/blob/master/request_validation_schema.json) which describes the acceptable JSON structure.
```json

[
  {
    "title": "First Section",
    "questions": [
      {
        "type": "input",
        "question": "Describe the condition of the kitchen.",
        "max_characters": 200
      },
      {
        "type": "boolean",
        "question": "Is the WiFi working?",
        "answers": [
          "Yes",
          "No"
        ]
      }
    ]
  }
]
```
You can validate your own output to ensure it is correct by using a website like https://www.jsonschemavalidator.net/ and the supplied [JSON Schema](https://github.com/shepper-tech/shepper-frontend-test/blob/master/request_validation_schema.json) which should highlight any structure or type issues.

## :eyes: Pointers
We're most interested in the architectural approach taken and patterns used, hence the loosely defined scope of the challenge. While the task only outlines two question types, theoretically more might be added in the future so we're keen to see a solution which factors this in and would easily scale without affecting maintainability.

We're also keen to see you demonstrate a good understanding of UI/UX, however the technical approach should be your primary focus so please feel free to use any UI libraries or CSS frameworks you're familiar with.

## :postbox: Submission
Feel free to either clone this repository or create your own private GitHub repository and when you're happy with your work just add me ([@nickma42](https://github.com/nickma42)) as a contributor.

Please include all necessary build steps and instructions required to run and validate your work.
