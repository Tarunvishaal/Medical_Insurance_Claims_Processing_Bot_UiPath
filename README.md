# Medical Insurance Claims Processing Bot

## Project Description

This project automates the processing of medical insurance claims by using UiPath to read and extract patient data from JSON files and fill out an insurance claims form. The responses from this form are then processed from a linked Google Sheet, and notifications are sent regarding the status of each claim.

## Features

- **Automated JSON Data Parsing**: Processes individual JSON files containing patient data.
- **Dynamic Form Filling**: Utilizes a custom Google Form to capture claims data.
- **Data Integration with Google Sheets**: Retrieves form responses stored in Google Sheets.
- **Email Notification**: Sends notifications regarding claim statuses via SMTP.

## Prerequisites

To run this project, you will need:
- UiPath Studio installed on your machine.
- Access to Google Workspace for handling Google Forms and Google Sheets.
- SMTP server access for sending emails.

## Installation

1. **Clone or download this repository** to your local machine.
2. **Open the project** in UiPath Studio.
3. **Install necessary packages** such as `UiPath.Mail.Activities` via Manage Packages.

## Setup

### Initial Configuration

1. **JSON Data Storage**: Place your JSON files in a designated folder. Each file should contain data related to a single patient's insurance claim.

### Data Source

The JSON files used as input data in this project are sourced from the Synthea dataset, a synthetic dataset generator for healthcare data. Currently, the project folder contains only two sample JSON files for demonstration purposes.

- **Additional Data**: If you require more sample data, you can download additional JSON files from the [Synthea dataset page](https://synthetichealth.github.io/synthea/).

### Google Workspace Setup

#### Custom Google Form
- **Reference Form**: The project currently includes an `Open Browser` activity configured with a link to a sample Claims Form. You can access this form for reference [here](https://forms.gle/EeBo3nBjPdCcG6BKA). This form is used as a template to demonstrate how the bot fills out a claims form.
- **Form Creation**: You are required to create your own Google Form tailored to your specific needs. After creating your form, update the URL in the `Open Browser` activity within the UiPath workflow to point to your new form.

#### Google Sheets Integration
- **Spreadsheet Link**: Link your Google Form to a new Google Sheet to capture responses automatically.
- **Connection Setup**: Configure the `Read Range` activity in UiPath to connect to your Google Sheets using your own Google account credentials.

### Email Configuration

1. **SMTP Settings**:
   - Configure the `Send SMTP Mail Message` activity using your SMTP server details.
   - Alternatively, you may choose any other method suitable for your needs to communicate the status of claims.

## Running the Project

Follow these steps to execute the workflow:
1. **Start the Bot**: Run the main workflow in UiPath Studio.
2. **Data Processing**: The bot will read each JSON file, fill out the online form, retrieve responses, and send status emails.

## Customization

- **Forms and Sheets**: You may need to adjust fields in the Google Form and the corresponding ranges in the Google Sheets based on your specific requirements.
- **Email Template**: Modify the email content and subject according to the needs of your recipients.

## Troubleshooting

For common setup issues, refer to the following:
- **Google API errors**: Ensure your Google projects are correctly set up with appropriate permissions.
- **SMTP errors**: Verify your server settings and credentials for accuracy.

## Contact Information

For further assistance or feedback, please contact tarun.vishaal@gmail.com.
