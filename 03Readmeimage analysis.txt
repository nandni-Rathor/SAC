Azure Vision API Text Extraction Tool

This project is a Python application that uses Azure’s AI Vision API to extract and display text from images. With this tool, users can upload images containing printed or handwritten text, which is then analyzed to identify and extract text. The tool provides bounding polygons around detected words, overlays this information onto the original image, and saves it as an annotated output image.

Features

Text Extraction: Reads printed or handwritten text from an image using Azure’s Vision API.
Bounding Box Overlay: Displays the detected text on the image with bounding polygons around each word for visualization.
Text Confidence Level: Outputs the confidence score for each word identified in the image.

Requirements:
Python 3.6+
Azure Vision API
Required packages (install with pip install -r requirements.txt):
dotenv: For loading environment variables from the .env file.
Pillow: For image processing.
matplotlib: For displaying the annotated images.
azure-ai-vision and azure-core for the Azure Vision client.
Setup

Azure Vision API Configuration:
Set up an Azure Vision service on Azure.
Retrieve your Azure Vision endpoint and key.

Environment Variables:
Create a .env file in the project directory with the following variables:
makefile
Copy code
AI_SERVICE_ENDPOINT="https://xxxxxx.cognitiveservices.azure.com/"
AI_SERVICE_KEY="xxxxxx"
Replace xxxxxx with your Azure Vision service endpoint and key.

Image Files:
Place images to analyze (e.g., Lincoln.jpg and Note.jpg) in a folder named images within the project directory.
Running the Application.

To run the program, execute the following command:
bash
Copy code
python read-text.py
Menu Options
When prompted:

Press 1 to analyze a sample image (Lincoln.jpg) for printed text.
Press 2 to analyze a sample image (Note.jpg) for handwritten text.
Press any other key to quit.

Code Explanation

Environment Loading: The application uses dotenv to load Azure credentials from the .env file.
Azure Client Initialization: An ImageAnalysisClient is created using the endpoint and key, allowing access to Azure’s Vision API.
Text Reading (GetTextRead):
The selected image is opened and analyzed by Azure’s Vision API to extract text and obtain bounding polygons.
Each line and word detected is printed with confidence scores.
The detected words are drawn on the image with bounding polygons for visualization.
Saving and Displaying the Image: The annotated image is displayed using matplotlib and saved as text.jpg in the project directory.

Output
The program saves the annotated image (text.jpg) in the project directory and prints detected text, bounding polygons, and confidence levels in the console.