**getEmployee**
----
  Returns the specified Employee.
  
  * **Version History:**

	TASS v54.0 - Method Added

	TASS v54.4 - Campus data has been added to the response

	TASS v57.11 - Ceider data has been added to the response

	TASS v60.02 - Alternate id has been added to the response

* **Version:**

  3

* **Permission:**

   Employee/HR > Employees > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `userid [string]`

   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
		{
			"user": {
					"mobPhone": "0412016500",
					"nokAdd2Text": "",
					"positionTitle": "Head of Senior School",
					"startDate": "04/09/2000",
					"postCode": 4000,
					"nokPostCode": 4020,
					"nokNameTest": "ssdtr",
					"add1Text": "114 Queen Street",
					"email": "AJ333@tassweb.com.au",
					"initialsText": "ASJ",
					"stateText": "QLD",
					"currentStatus": "current",
					"schoolEmail": "AJSCHOOL@TASSWEB.COM",
					"supervisor2Code": "",
					"tchCode": "AJ",
					"salutationFlag": "Mr",
					campus": [
					"Senior School (Curlew St)"
					],
					"nokCountryText": "AU 333",
					"phoneHText": "123456789 333",
					"givenNamesText": "Alan Fred",
					"username": "ajohnstone",
					"isTeacher": true,
					"preferNameText": "Al",
					"id": 1000016,
					"nokCityText": "KIPPA RING",
					"statusText": "F",
					"nokPhoneHText": "123456789 333",
					"termDate": "",
					"cityText": "BRISBANE",
					"nokPhoneWText": "123456789 333",
					"positionText": "Teacher",
					"nameSuffix": "BA, DipTch (MIT), QCT",
					"dpidText": "",
					"sexFlag": "U",
					"smsFlg": "Y",
					"empCode": 1000016,
					"nokrelatText": "Slave",
					"phoneWText": "123456789 333",
					"supervisorCode": "",
					"surnameText": "Johnstone",
					"add2Text": "Bowen Hills",
					"nokAdd1Text": "Borella Circuit",
					"countryText": "",
					"superNoText": "",
					"nokStateText": "QLD",
					"tchName": "Mr A O'Johnstone",
					"ceider": 11540,
					"alternateId": ""
			},
			"__tassversion": "01.057.11.000",
			"token": {
					"timestamp": "{ts '2022-09-28 16:32:57'}",
					"userid": 1000016
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
	
* **Sample Parameters:**

  	```javascript
		{'userid':'1000016'}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getEmployee&appcode=DEMOOLIVER&company=10&v=3&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getEmployee">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="3">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
