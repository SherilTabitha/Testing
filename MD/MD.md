| Id | Test Case Name | Status | Type | Description | Pre Condition | Test Step# | Test Step Description | Test Step Expected Result | Test Case Type | Application Team | Functionality | Assigned To | Priority | Automation Status | Creation Date |
\
|----|-----------------|--------|------|-------------|---------------|------------|----------------------|--------------------------|----------------|------------------|--------------|-------------|----------|-------------------|---------------|
\
| TC01_API_Positive_01 | Successful Ticket Booking | Not Executed | Automation | Validate successful booking via /api/tickets/book with valid input (e.g., user_id, event_id, seat_number, payment_info). | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Positive | Team A | Ticket Booking API | Team A | High | Automated | 2024-06-12 |
\
||||||||2|Send a valid POST request with all required fields (user_id, event_id, seat_number, payment_info)|Request is accepted by the API|Positive|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||3|Verify the API returns HTTP 201 Created|Response status is 201 Created|Positive|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||4|Verify the JSON response contains booking_id, event_details, seat_number, booking_status: 'confirmed'|Response contains all required fields with booking_status as 'confirmed'|Positive|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
| TC02_API_Negative_01 | Booking with Missing Required Field | Not Executed | Automation | Validate API response when a required field (e.g., seat_number) is missing in the POST request. | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Negative | Team A | Ticket Booking API | Team A | High | Automated | 2024-06-12 |
\
||||||||2|Send a POST request missing the seat_number field|API should return HTTP 400 Bad Request|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||3|Verify the error message specifies the missing field|Error message clearly identifies missing seat_number|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
| TC03_API_Negative_02 | Booking with Invalid Payment Info | Not Executed | Automation | Validate API response when payment_info is invalid (e.g., expired card). | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Negative | Team A | Ticket Booking API | Team A | High | Automated | 2024-06-12 |
\
||||||||2|Send a POST request with invalid payment_info (e.g., expired card)|API should return HTTP 402 Payment Required|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||3|Verify the error message specifies invalid payment|Error message clearly identifies invalid payment_info|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
| TC04_API_Negative_03 | Booking with Duplicate Seat | Not Executed | Automation | Validate API response when booking a seat that is already booked. | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Negative | Team A | Ticket Booking API | Team A | High | Automated | 2024-06-12 |
\
||||||||2|Send a POST request for a seat_number that is already booked|API should return HTTP 409 Conflict|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||3|Verify the error message specifies seat already booked|Error message clearly identifies duplicate seat booking|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
| TC05_API_Negative_04 | Booking with Invalid Event ID | Not Executed | Automation | Validate API response when event_id does not exist. | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Negative | Team A | Ticket Booking API | Team A | High | Automated | 2024-06-12 |
\
||||||||2|Send a POST request with an invalid event_id|API should return HTTP 404 Not Found|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
||||||||3|Verify the error message specifies event not found|Error message clearly identifies invalid event_id|Negative|Team A|Ticket Booking API|Team A|High|Automated|2024-06-12|
\
| TC06_API_Regression_01 | Regression: Booking with Valid Data After Failure | Not Executed | Automation | Ensure booking succeeds with valid data after a failed attempt (e.g., after negative test case). | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Positive | Team A | Ticket Booking API | Team A | Medium | Automated | 2024-06-12 |
\
||||||||2|Send a valid POST request after a failed booking attempt|API should return HTTP 201 Created|Positive|Team A|Ticket Booking API|Team A|Medium|Automated|2024-06-12|
\
||||||||3|Verify the booking is confirmed and not affected by previous failure|Booking is successful and independent of previous failed attempt|Positive|Team A|Ticket Booking API|Team A|Medium|Automated|2024-06-12|
\
| TC07_API_Regression_02 | Regression: Booking API Stability Under Load | Not Executed | Automation | Ensure API remains stable and responsive under multiple concurrent booking requests. | API endpoint /api/tickets/book is active | 1 | Open the API endpoint /api/tickets/book | API endpoint should be accessible | Positive | Team A | Ticket Booking API | Team A | Medium | Automated | 2024-06-12 |
\
||||||||2|Send multiple concurrent valid POST requests|API should handle requests without errors or crashes|Positive|Team A|Ticket Booking API|Team A|Medium|Automated|2024-06-12|
\
||||||||3|Verify all successful bookings are processed correctly|All bookings are confirmed with unique booking_id|Positive|Team A|Ticket Booking API|Team A|Medium|Automated|2024-06-12|
\

\
**Metrics:**
\
- Total Test case created: 7
\
- Functional Positive Test cases count: 1
\
- Functional Negative Test cases count: 4
\
- Regression Test cases count: 2