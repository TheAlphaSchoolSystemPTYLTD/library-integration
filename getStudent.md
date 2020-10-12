**getStudent**
----
  Returns the specified Student.
  
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
 
   `userid [string]`

   **Optional:**
 
   none

   **Conditional:**

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
			"scholasticYearDesc": 11,
			"firstName": "Andréa Joan",
			"studCode": "0009130",
			"preferred_surname": "Clark",
			"dateOfLeaving": "",
			"currentStatus": "current",
			"alternateId": "098765432",
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
	
* **Sample Parameters:**

  ```javascript
	{
		'userid':'0009130',
		'commtype':'TK'
	}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getStudent&appcode=DEMOOLIVER&company=10&v=3&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getStudent">
	  <input type="hidden" name="appcode" value="DEMOOLIVER">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="3">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
