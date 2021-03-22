**getStudents**
----
  Returns an array of Students.

* **Version History:**

	TASS v54.0 - Method Added

* **Version:**

	3

* **Permission:**

   Student Records > Students > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `currentstatus [string]` - can only be 'current' or 'noncurrent'
   
   **Optional:**
 
   `codeonly [boolean]` - can only be 'true' or 'false' to return employee or student code only

   `commtype [string]` - Communication Rule Type. Must be one of:
    ```HTML
        all - Communication Types
        aca – Academic Reports
        att – Attendance
        ec – Emergency Contact
        gen – TASS.web Correspondence
        lw – Student Lives With
        tk – Teacher Kiosk View
        tkco – Teacher Kiosk Correspondence
    ```

   `updateafter [date]` - Update After date

   `includefuture [boolean]` - can only be 'true' or 'false'

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
		{
			"users": [
					{
						"dateOfExpiry": "",
						"surname": "Agnew",
						"mobilePhone": "0412016500",
						"scholasticYear": 11,
						"pcTutorGroup": "AS",
						"preferredName": "Edie",
						"emailAddress": "agnew2@alphabus.com.au",
						"ceider": 2,
						"scholasticYearDesc": 11,
						"firstName": "Edith Nell Blue Healer Bitzer Edith Nell Other Bell Nell",
						"campus": [
						"Senior School (Curlew St)"
						],
						"studCode": "0009069",
						"preferred_surname": "Agnew",
						"dateOfLeaving": "",
						"currentStatus": "current",
						"alternateId": "",
						"first_name": "Edith Nell Blue Healer Bitzer",
						"updateOn": "14/07/2020",
						"other_name": "Edith Nell Other Bell Nell",
						"username": "",
						"gender": "U",
						"birthday": "02/05/1988",
						"rollClass": "",
						"addresses": [
									{
										"mobile2": "",
										"parent1": {
													"initials": "M",
													"suffix": "",
													"surname": "Agnew",
													"description": "Mother/Parent 1",
													"preferred_name": "Mary",
													"other_name": "",
													"title": "",
													"first_name": "Mary"
										},
										"postCode": 4030,
										"parentType": "TER",
										"parent2": {
													"initials": "M",
													"suffix": "",
													"surname": "Agnew",
													"description": "Father/Parent 2",
													"preferred_name": "Mary",
													"other_name": "",
													"title": "",
													"first_name": "Mary"
										},
										"commtypeTkco": "Y",
										"email": "",
										"homePhone": "374 2252",
										"parentCode": "000003",
										"smsFlag2": "N",
										"smsFlag1": "Y",
										"commtypeTk": "Y",
										"country": "",
										"stateCode": "QLD",
										"commtypeTkDesc": "Teacher Kiosk View",
										"parentName": "Mr & Mrs G. Agnew",
										"salutation": "",
										"personPosition": "",
										"commtypeEc": "Y",
										"fatherName": "George Agnew",
										"commtypeGenDesc": "TASS.web Correspondence",
										"mobile1": "0612016500",
										"address1": "",
										"addressDescription": "Postal",
										"address3": "",
										"reltagCode": "",
										"commtypeAca": "Y",
										"address2": "1/54 Kitchener Road",
										"surname": "Agnew",
										"commtypeLw": "N",
										"addressNumber": 1,
										"townSuburb": "LUTWYCHE",
										"commtypeAttDesc": "Attendance",
										"commtypeEcDesc": "Emergency Contact",
										"email2": "",
										"dpidText": "",
										"reltagDescription": "",
										"commtypeGen": "Y",
										"commtypeTkcoDesc": "Teacher Kiosk Correspondence",
										"commtypeAcaDesc": "Academic Reports",
										"motherName": "Mary Agnew",
										"positionLabel": "",
										"businessPhone": "221 9898",
										"fax": "",
										"parentName2": "",
										"commtypeAtt": "Y",
										"commtypeLwDesc": "Student Lives With"
									}
						]
					}
			],
			"__tassversion": "01.053.3.138",
			"token": {
					"timestamp": "{ts '2021-01-20 16:10:40'}",
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
	
	`date` not a valid date
	```javascript
	__invalid: {
	  [field_name]: "Value is not a valid date."
	}
	```

	`currentstatus` not 'current' or 'noncurrent'
	```javascript
	__invalid: {
	  [field_name]: "'currentstatus' MUST BE 'current' or 'noncurrent'"
	}
	```

	`commtype` is supplied, but `type` is not 'S'
	```javascript
	__invalid: {
	  "commtype": "'commtype' IS ONLY VALID WHERE 'type' IS 'S'"
	}
	```

	`updateafter` is supplied, but `type` is not 'S'
	```javascript
	__invalid: {
	  "updateafter": "'updateafter' IS ONLY VALID WHERE 'type' IS 'S'"
	}
	```

	`codeonly` not a valid boolean
	```javascript
	__invalid: {
	  [field_name]: "'codeonly' MUST BE 'true' or 'false'"
	}
	```

	`includefuture` not a valid boolean
	```javascript
	__invalid: {
	  [field_name]: "'includefuture' MUST BE 'true' or 'false'"
	}
	```

	`includefuture` is supplied, but `type` is not 'S'
	```javascript
	__invalid: {
	  "includefuture": "'includefuture' IS ONLY VALID WHERE 'type' IS 'S'"
	}
	```
	
* **Sample Parameters:**

  ```javascript
	{
		'currentstatus':'current'
	}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getStudents&appcode=DEMOOLIVER&company=10&v=1&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getStudents">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="1">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
