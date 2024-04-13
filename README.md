# apollolytics-CSCW

**Manual for using Apollolytics**


**Introduction**

This manual explains how to analyze social media data for propaganda using a predefined FastAPI server. You'll send requests with JSON payloads via cURL to detect propaganda techniques, fact-check statements, and gain analytical insights.

**1. Usage via CURL**

Here's a breakdown of the cURL command:

```bash
curl -X POST http://13.48.71.178:8000/analyze_propaganda \
     -H 'Accept: application/json' \
     -H 'Content-Type: application/json' \
     -d @data/sample_payload.json
```
Here is an explanation of the given request:

* X POST: HTTP method for sending data.
http://13.48.71.178:8000/analyze_propaganda: Server address and endpoint for propaganda analysis.
+ -H 'Accept: application/json': Tells the server you want results in JSON format.
* -H 'Content-Type: application/json': Specifies your data is JSON-formatted.
* -d @sample_payload.json: Loads payload from the sample_payload.json file.


**2. Interacting with Swagger UI**

You can also reach the API via the Swagger UI via http://13.48.71.178:8000/docs


Once you open the Swagger UI in your browser, you will see a list of all available endpoints defined in your FastAPI application. Here's how to use it for your propaganda analysis task:

* **Explore the Endpoints:** Swagger UI will display each endpoint with a brief description if provided in the FastAPI code. Look for the `/analyze_propaganda` endpoint and expand it.

* **Understand Parameters:**  Swagger UI will show you:
    * **Required Parameters:**  Fields like `model_name`, `text`, and `fact_checking`.
    * **Data Types:** Whether a parameter should be a string, boolean, etc.

* **Try Out an Endpoint:**
    1. Click the "Try it out" button under the `/analyze_propaganda` endpoint.
    2. Enter a value for the `model_name` (e.g., "gpt-3.5-turbo").
    3. Paste a social media text snippet into the `text` field.
    4. Set `fact_checking` to `true` or `false`.

* **Execute the Request:** Click the "Execute" button. Swagger UI will:
    * Send the request to your FastAPI server.
    * Display the response, including:
        * **Status Code:** (e.g., 200 for success)
        * **Response Body:**  The JSON data returned by the analysis.
