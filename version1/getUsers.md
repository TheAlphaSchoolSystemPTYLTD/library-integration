**getUsers**
----
  Returns an array of Users.
  
* **Version History:**

	TASS v49.7 (PR9) - New field ("pcTutorGroup") added to the data returned.

	TASS v51.4 (PR4) - New Property `email2` added to the data returned.

	TASS v52.0 - Return 3 new fields `preferred_surname`, `first_name`, `other_name` for each student. Return 16 new fields `m_description`, `m_title`, `m_initials`, `m_surname`, `m_first_name`, `m_other_name`, `m_preferred_name`, `m_suffix`, `f_description`, `f_title`, `f_initials`, `f_surname`, `f_first_name`, `f_other_name`, `f_preferred_name`, `f_suffix` for parent1 & parent2 per address per user.

	TASS v52.7 - New Properties `alternateId` & `scholasticYearDesc` added to the data returned.

	TASS v54.4 - Campus data has been added to the response

* **Version:**

  1

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `type [string]`

   `currentstatus [string]` - can only be 'current' or 'noncurrent'
   
   **Optional:**
 
   `codeonly [boolean]` - can only be 'true' or 'false' to return employee or student code only

   **Conditional:**

   `commtype [string]` - Communication Rule Type. Only valid where `type` is 'S'. Must be one of:
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

   `updateafter [date]` - only valid where `type` is 'S'

   `includefuture [boolean]` - only valid where `type` is 'S', and can only be 'true' or 'false'

* **Success Response:**
	
	```javascript
	"users": [
			{
				"dateOfExpiry": "",
				"surname": "Clark",
				"mobilePhone": "0439443653                    ",
				"scholasticYear": -3,
				"pcTutorGroup": "B1Z",
				"preferredName": "Lauren",
				"emailAddress": "clark@tassweb.com.au",
				"ceider": 1951,
				"scholasticYearDesc": 11,
				"firstName": "Lauren Jane",
				"studCode": "0009134",
				"preferred_surname": "Clark",
				"dateOfLeaving": "",
				"currentStatus": "current",
				"alternateId": "098765432",
				"first_name": "Lauren",
				"campus": [
				"Senior School (Curlew St)"
				],
				"updateOn": "05/04/2019",
				"other_name": "Jane",
				"username": "ajohnstone1",
				"gender": "F",
				"addresses": [
					{
						"mobile2": "0412016500",
						"m_initials": "P",
						"m_suffix": "suf",
						"m_surname": "Clark",
						"m_description": "Mother/Parent 1",
						"m_preferred_name": "Paula",
						"m_other_name": "PauOth",
						"m_title": "Mrs",
						"m_first_name": "Paula",
						"postCode": 4005,
						"parentType": "TER",
						"f_initials": "E",
						"f_suffix": "",
						"f_surname": "Clark",
						"f_description": "Father/Parent 2",
						"f_preferred_name": "Edward",
						"f_other_name": "",
						"f_title": "",
						"f_first_name": "Edward",
						"commtypeTkco": "N",
						"email": "t.sloman84@gmail.com",
						"homePhone": "3870 9987",
						"parentCode": "000055",
						"smsFlag2": "Y",
						"smsFlag1": "Y",
						"commtypeTk": "Y",
						"country": "AUSTRALIA",
						"stateCode": "QLD",
						"commtypeTkDesc": "Teacher Kiosk View",
						"parentName": "Mrs E Clark PNE",
						"salutation": "Mr and Mrs Clark",
						"personPosition": "",
						"commtypeEc": "N",
						"fatherName": "Edward Clark",
						"commtypeGenDesc": "TASS.web Correspondence",
						"mobile1": "0427203657",
						"address1": "",
						"addressDescription": "Correspondence",
						"address3": "Addr Line 3",
						"reltagCode": "",
						"commtypeAca": "N",
						"address2": "123 Smith Rd",
						"surname": "Clark",
						"commtypeLw": "N",
						"addressNumber": 1,
						"townSuburb": "ALBION",
						"commtypeAttDesc": "Attendance",
						"commtypeEcDesc": "Emergency Contact",
						"email2": "fang.guo@tassweb.com",
						"dpidText": "",
						"reltagDescription": "",
						"commtypeGen": "N",
						"commtypeTkcoDesc": "Teacher Kiosk Correspondence",
						"commtypeAcaDesc": "Academic Reports",
						"motherName": "Paula Clark",
						"positionLabel": "",
						"businessPhone": "3201 1302",
						"fax": "375575756576",
						"parentName2": "",
						"commtypeAtt": "N",
						"commtypeLwDesc": "Student Lives With"
					},
					{
						"mobile2": "0412016500",
						"m_initials": "P",
						"m_suffix": "suf",
						"m_surname": "Clark",
						"m_description": "Mother/Parent 1",
						"m_preferred_name": "Paula",
						"m_other_name": "PauOth",
						"m_title": "Mrs",
						"m_first_name": "Paula",
						"postCode": 4010,
						"parentType": "TER",
						"f_initials": "E",
						"f_suffix": "",
						"f_surname": "Clark",
						"f_description": "Father/Parent 2",
						"f_preferred_name": "Edward",
						"f_other_name": "",
						"f_title": "",
						"f_first_name": "Edward",
						"commtypeTkco": "N",
						"email": "paripper@bigpond.com; edward_clarke@alphabus.com.au",
						"homePhone": "3870 9987",
						"parentCode": "000055",
						"smsFlag2": "Y",
						"smsFlag1": "N",
						"commtypeTk": "Y",
						"country": "",
						"stateCode": "SA",
						"commtypeTkDesc": "Teacher Kiosk View",
						"parentName": "Mr E.&R Clark# A.K.A %%Wellington",
						"salutation": "Mr Clark (Father 7)",
						"personPosition": 2,
						"commtypeEc": "N",
						"fatherName": "Edward Clark",
						"commtypeGenDesc": "TASS.web Correspondence",
						"mobile1": "",
						"address1": "Fathers Address",
						"addressDescription": "Father's Address",
						"address3": "",
						"reltagCode": "",
						"commtypeAca": "N",
						"address2": "PO Box #18",
						"surname": "Clark",
						"commtypeLw": "N",
						"addressNumber": 7,
						"townSuburb": "WINDSOR",
						"commtypeAttDesc": "Attendance",
						"commtypeEcDesc": "Emergency Contact",
						"email2": "email2clark@alphabus.com.au",
						"dpidText": "",
						"reltagDescription": "Biological",
						"commtypeGen": "N",
						"commtypeTkcoDesc": "Teacher Kiosk Correspondence",
						"commtypeAcaDesc": "Academic Reports",
						"motherName": "Paula Clark",
						"positionLabel": "Father/Parent 2",
						"businessPhone": "33201 1301",
						"fax": "33201 5545",
						"parentName2": "",
						"commtypeAtt": "N",
						"commtypeLwDesc": "Student Lives With"
					}
				],
				"birthday": "02/09/1994",
				"rollClass": "A"
			}
			"__tassversion": "01.053.3.138",
			"token": {
					"commtype": "TK",
					"timestamp": "{ts '2021-03-24 09:43:45'}",
					"currentstatus": "current",
					"type": "S"
			}
		]
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
	type=S&commtype=TK&currentstatus=current
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getUsers&appcode=DEMOOLIVER&company=10&v=1&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getUsers">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="1">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
