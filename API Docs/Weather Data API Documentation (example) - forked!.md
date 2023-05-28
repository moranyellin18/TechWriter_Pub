Weather Data API Documentation
Version: 1.0

Introduction
--------------
The Weather Data API provides access to real-time weather information for various locations around the world. This documentation serves as a guide for developers to understand and utilize the API effectively.

Base URL
--------------
The base URL for accessing the Weather Data API is:
https://api.weatherdata.com/v1/

Authentication
--------------
To make API requests, you need to include your API key in the request headers. The API key should be included in the "Authorization" header with the format: "Bearer {API_KEY}".

Endpoints
--------------
1. Get Current Weather
   Endpoint: /current
   Method: GET
   Description: Retrieves the current weather conditions for a specific location.
   Parameters:
     - location: The name or coordinates of the location.
   Example Request:
     GET /current?location=New%20York,%20USA
   Example Response:
     {
       "location": "New York, USA",
       "temperature": 22.5,
       "humidity": 67,
       "conditions": "Partly cloudy"
     }

2. Get Forecast
   Endpoint: /forecast
   Method: GET
   Description: Retrieves the weather forecast for a specific location.
   Parameters:
     - location: The name or coordinates of the location.
     - days: The number of days for the forecast (1-7).
   Example Request:
     GET /forecast?location=London,%20UK&days=3
   Example Response:
     {
       "location": "London, UK",
       "forecast": [
         {
           "date": "2023-05-24",
           "temperature": {
             "min": 15,
             "max": 22
           },
           "conditions": "Rain"
         },
         {
           "date": "2023-05-25",
           "temperature": {
             "min": 14,
             "max": 19
           },
           "conditions": "Cloudy"
         },
         {
           "date": "2023-05-26",
           "temperature": {
             "min": 16,
             "max": 21
           },
           "conditions": "Partly cloudy"
         }
       ]
     }

Error Handling
--------------
The API returns appropriate HTTP status codes for different scenarios. In case of an error, the response body will contain an error message providing more details about the issue.

Rate Limiting
--------------
The API has a rate limit of 1000 requests per hour. If you exceed the limit, you will receive a "429 Too Many Requests" response. Make sure to handle rate limiting in your application.

Conclusion
--------------
This API documentation provides an overview of the Weather Data API endpoints, parameters, and response structures. Use the provided endpoints to access real-time weather information for your applications.

For further information or support, please contact our API support team at support@weatherdata.com.
