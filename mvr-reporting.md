# Automation Reporting Feature

The Automation Reporting feature is available on all MediCapture MVR and MTR device models. The recommended firmware version is FW 250924 or newer.

## 1. Report Description

### Report Structure

- Report Header Image (Present only on the first page).
- Institution Name and Location.
- Device Name, Model, Device ID, and Firmware Version of the device used to create the report.
- Patient Last and First name.
- Patient ID Number.
- Patient Gender.
- Patient Birth Date.
- Performing Physician.
- Study/Series Description.
- Case Folder Name (unique name constructed of the time stamp and Device ID).
- Report Creation Date.
- Current/Total Number of Report Pages.
- Image File Name.
- Image Captured Date.
- Image Notes. Created in Image Review.
- Image to Report. Annotation was done in Image Review.
- Report Notes. Ending notes. Written using Markdown.
- Institution Stamp or Physician Signature.
- Footer Text (present at the bottom of every page).
  The header table (items 2-12) will be displayed on every page to ensure traceability and prevent pages from being mixed up.

## 2. Creating a Report

To generate a new report, follow these steps:

- Go to the Archive and find the case folder you wish to use.

- Open the folder and select the images you want to include in the report. You can choose any number of images before or after entering the Report screen. You must select at least one image to create a report.

- Press the "Report" button.

- Adjust the general report settings as needed.

- Click "Save" to save the report as a PDF in the same folder, or click "Print" to send it directly to a connected printer.
  Click "Save" to save the report as a PDF in the same folder, or click "Print" to send it directly to a connected printer.
  
  - Note: To exit the print menu, either swipe left on the screen or choose "Cancel Print" and then press the "<" arrow button.

- Alternatively, in Archive mode, tap on the Report button to create a report that includes all images in the selected study folder.

## 3. Report Customization

You can customize the appearance of your reports using a variety of settings.

### General Settings

These settings are adjusted after you enter the "Report" screen and apply to the current report you are creating.

- Page Layout: Choose the page orientation and the number of images per page.
  Page Layout: Choose the page orientation and the number of images per page.
  
  - Portrait: 1, 2, 3, 6 (2 x 3), or 8 (2 x 4) images per page.
  - Landscape: 1, 4 (2 x 2), or 9 (3 x 3) images per page.

- Page Size: Select a standardized size for your report and printing (e.g., ISO A4, Letter, ISO A3, ISO A5, ISO A6, or 100 x 148 mm (Hagaki).

- Mode: Choose one of three modes:
  Mode: Choose one of three modes:
  
  - Default: Standard report with all information.
  - Anonymize: Excludes all patient information.
  - Only images: The report contains only images with no accompanying text.

- Notes: Add or adjust existing notes in Markdown format. These notes will appear at the end of the report after the images (item 17).

### Report Settings and Presets

The Report settings allow you to create a preset, so your preferred settings are applied to every future report. To access these settings, navigate to Settings > Archive > Report Settings, or from the "Report" screen, click the Report settings button in the top right.

- Report preview: View a simulated version of a report before it's finalized. Patient info excluded.
- Header image (1): Upload an image in JPG or PNG format from the root folder of the USB storage to be used as a header on the first page of the report. The recommended image resolution is around 2048 x 256, or an approximate aspect ratio of 8:1 to 10:1. The image will be scaled to fit the page width.
- Image at the end of the report (18): Upload an image from the root folder of USB storage to appear after the notes (e.g., a doctor's signature or hospital stamp). The recommended image resolution is around 2048 x 256, or an approximate aspect ratio of 8:1 to 10:1. The image will be scaled to fit the page width.
- Footer text (19): Write text with Markdown to be placed at the bottom left of each page.
- Notes text (17): Create a default Markdown note that will automatically appear at the end of every report. This note will be used as a template and can be edited for individual reports by tapping Notes.
- Page Layout and Page Size: These settings function the same as the general settings, but apply as a default for all future reports.
- Auto reporting: When enabled, a report will be created automatically after each study. You can choose to automatically save it as a PDF in the case folder or open the print directory. This feature is disabled by default.

## 4. Notes

- To set up the institution name, Department name, Location, and Device title, navigate to Settings > System > Patient info.
- Following your medical institution's document formatting guidelines, you might need to format your document in Markdown. Here's a quick cheat sheet for common Markdown formatting.
