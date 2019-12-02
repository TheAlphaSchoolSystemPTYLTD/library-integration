**getUser**
----
  Returns the specified User.
  
  * **Version History:**

	TASS v49.7 (PR9) - New field ("pcTutorGroup") added to the data returned.

	TASS v51.4 (PR4) - New Property `email2` added to the data returned.

	TASS v52.0 - Return 3 new fields `preferred_surname`, `first_name`, `other_name` for each student. Return 16 new fields `m_description`, `m_title`, `m_initials`, `m_surname`, `m_first_name`, `m_other_name`, `m_preferred_name`, `m_suffix`, `f_description`, `f_title`, `f_initials`, `f_surname`, `f_first_name`, `f_other_name`, `f_preferred_name`, `f_suffix` for parent1 & parent2 per address.

* **Version:**

  1

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `userid [string]`

   `type [string]`
   
   **Optional:**
 
   none

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

* **Success Response:**
	
	```javascript
	{
		"__status": "success",
		"__invalid": {},
		"__locks": {},
		"user": {
			"dateOfExpiry": "",
			"surname": "Clark",
			"mobilePhone": "0025632532",
			"scholasticYear": 11,
			"pcTutorGroup": "9D",
			"preferredName": "Andy",
			"emailAddress": "peter.ripper@tassweb.com.au",
			"ceider": "23wrrthhw",
			"firstName": "Andréa Joan",
			"studCode": "0009130",
			"preferred_surname": "Clark",
			"dateOfLeaving": "",
			"currentStatus": "current",
			"first_name": "Andréa",
			"updateOn": "31/07/2019",
			"other_name": "Joan",
			"username": "aclarke",
			"gender": "F",
			"addresses": [
				{
					"mobile2": "0995 111 222",
					"m_initials": "P",
					"m_suffix": "suf",
					"m_surname": "Clark",
					"m_description": "Mother/Parent 1",
					"m_preferred_name": "Paula",
					"m_other_name": "PauOth",
					"m_title": "Mrs",
					"m_first_name": "Paula",
					"postCode": 4053,
					"townSub": "STAFFORD",
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
					"email": "paripper@gmail.com",
					"homePhone": "870 9987",
					"parentCode": "000055",
					"smsFlag2": "N",
					"smsFlag1": "Y",
					"commtypeTk": "Y",
					"country": "",
					"stateCode": "TAS",
					"commtypeTkDesc": "Teacher Kiosk View",
					"parentName": "Mrs Nose.E. Neighbour",
					"salutation": "Hey You",
					"personPosition": "",
					"commtypeEc": "N",
					"fatherName": "Edward Clark",
					"commtypeGenDesc": "TASS.web Correspondence",
					"mobile1": "0488067672",
					"address1": "Alt Emergency Address",
					"addressDescription": "Alt emergency",
					"address3": "",
					"reltagCode": "",
					"commtypeAca": "N",
					"address2": "34 Dunedoo St",
					"surname": "Clark",
					"commtypeLw": "N",
					"addressNumber": 8,
					"commtypeAttDesc": "Attendance",
					"commtypeEcDesc": "Emergency Contact",
					"email2": "",
					"dpidText": "",
					"reltagDescription": "",
					"commtypeGen": "N",
					"commtypeTkcoDesc": "Teacher Kiosk Correspondence",
					"commtypeAcaDesc": "Academic Reports",
					"motherName": "Paula Clark",
					"positionLabel": "",
					"businessPhone": "201 1301",
					"fax": "201 5545",
					"parentName2": "",
					"commtypeAtt": "N",
					"commtypeLwDesc": "Student Lives With"
				}
			],
			"birthday": "02/09/1994",
			"rollClass": "D"
		},
		"token": {
			"commtype": "TK",
			"timestamp": "{ts '2019-11-27 15:06:41'}",
			"userid": "0009130",
			"type": "S"
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

	`commtype` is supplied, but `type` is not 'S'
	```javascript
	__invalid: {
	  "commtype": "'commtype' IS ONLY VALID WHERE 'type' IS 'S'"
	}
	```
	
* **Sample Parameters:**

  ```javascript
	userid=0009130&type=S&commtype=TK
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getUser&appcode=DEMOOLIVER&company=10&v=1&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getUser">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="1">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
