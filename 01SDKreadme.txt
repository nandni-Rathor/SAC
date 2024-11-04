1. The code file contains two implementations for detecting the language of user input text using Azure’s Text Analytics API.
   
2. Each implementation demonstrates a different approach:
   - **First**: Uses direct HTTP requests with the `http.client` module.
   - **Second**: Uses the Azure SDK via `azure.ai.textanalytics`.

### First Implementation (HTTP Requests with `http.client`)

3. Loads Azure service endpoint and API key from environment variables using `dotenv`.
   
4. Prompts the user to enter text repeatedly until they type "quit."
   
5. For each input:
   - Constructs a JSON body with the text.
   - Prepares the endpoint URI by removing "https://".
   - Establishes a connection using `http.client.HTTPSConnection`.
   - Sends a POST request to the Azure Text Analytics API (`/text/analytics/v3.1/languages?`) with JSON data and the API key in the header.
   
6. Processes the response:
   - If successful, decodes and parses the JSON response, extracting and printing the detected language.
   - If unsuccessful, handles the error by displaying the response or an error message.

7. This implementation shows lower-level HTTP request handling, including crafting headers and handling responses manually.

### Second Implementation (Azure SDK with `TextAnalyticsClient`)

8. Loads the endpoint and API key from environment variables.

9. Initializes `TextAnalyticsClient` with `AzureKeyCredential` for built-in authentication.

10. For each user input:
    - Calls `detect_language()` directly with the text.
    - Receives a structured response containing the detected language, which is printed.

11. This approach reduces complexity by handling authentication, request construction, and response parsing within the SDK, making it easier to maintain and closer to production standards for Azure services.

### Common Aspects of Both Implementations

12. Both implementations allow continuous user input until "quit" is entered.

13. The code demonstrates flexibility by showing both a low-level HTTP approach and a high-level SDK-based approach, offering options based on the developer's needs or control preferences.