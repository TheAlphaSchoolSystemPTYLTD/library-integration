**getEmployees**
----
  Returns an array of Employees.

* **Version History:**

	TASS v54.0 - Method Added

* **Version:**

	3

* **Permission:**

   Employee/HR > Employees > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `currentstatus [string]` - can only be 'current' or 'noncurrent'
   
   **Optional:**
 
   `codeonly [boolean]` - can only be 'true' or 'false' to return employee code only

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
		{
			"users": [
					{
						"mobPhone": "0426505880",
						"nokAdd2Text": "8 Land Street",
						"positionTitle": "",
						"startDate": "03/05/1995",
						"postCode": 4023,
						"nokPostCode": 4066,
						"nokNameTest": "Alan C",
						"add1Text": "1 Calculon Terrace",
						"email": "C.Allan@alphabus.com.au",
						"initialsText": "CE",
						"stateText": "QLD",
						"currentStatus": "current",
						"schoolEmail": "Cody.Allan@alphabus.com.au",
						"supervisor2Code": "",
						"tchCode": "CAL",
						"salutationFlag": "Capt",
						"campus": [
						"Argyle Street Campus",
						"Junior School (Billabong Road)",
						"Just made it up campus with 12",
						"Senior School (Curlew St)",
						"Thompson Street Campus"
						],
						"nokCountryText": "",
						"phoneHText": "07 3419 3693",
						"givenNamesText": "Cody Ethan",
						"username": "",
						"isTeacher": true,
						"preferNameText": "Cody",
						"id": 9000001,
						"nokCityText": "TOOWONG",
						"statusText": "F",
						"nokPhoneHText": "",
						"termDate": "",
						"cityText": "BOWEN HILLS",
						"nokPhoneWText": "",
						"positionText": "",
						"nameSuffix": "",
						"dpidText": "",
						"sexFlag": "U",
						"smsFlg": "Y",
						"empCode": 9000001,
						"nokrelatText": "Buddy",
						"phoneWText": "07 3550 7398",
						"supervisorCode": 1000016,
						"surnameText": "Allan",
						"add2Text": "left hand side",
						"nokAdd1Text": "Unit 810",
						"countryText": "",
						"superNoText": "",
						"nokStateText": "QLD",
						"tchName": "Mr C Allan"
					}
			],
			"__tassversion": "01.053.3.138",
			"token": {
						"timestamp": "{ts '2021-01-20 16:00:16'}",
						"currentstatus": "current"
			}
		}
  ```
 
* **Error Response:**

	Required `[field_name]` not supplied
	```javascript
	__invalid: {
	  [field_name]: "field is required."
	}
	```

	`currentstatus` not 'current' or 'noncurrent'
	```javascript
	__invalid: {
	  [field_name]: "'currentstatus' MUST BE 'current' or 'noncurrent'"
	}
	```

	`codeonly` not a valid boolean
	```javascript
	__invalid: {
	  [field_name]: "'codeonly' MUST BE 'true' or 'false'"
	}
	```
* **Sample Parameters:**

  	```javascript
	{'currentstatus':'current'}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getEmployees&appcode=DEMOOLIVER&company=10&v=1&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getEmployees">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="1">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
