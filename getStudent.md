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
			"user": {
					"dateOfExpiry": "",
					"surname": "Clark",
					"mobilePhone": "0426505880",
					"scholasticYear": 11,
					"pcTutorGroup": "9DD",
					"preferredName": "Andy",
					"emailAddress": "jason.jiang@tassweb.com.au",
					"ceider": "23wrrthhw",
					"scholasticYearDesc": 11,
					"firstName": "Andréa Joan",
					"campus": [
					"Banana Cmpy 10 Campus"
					],
					"studCode": "0009130",
					"preferred_surname": "Clark",
					"dateOfLeaving": "",
					"currentStatus": "current",
					"alternateId": "%BDMITC?",
					"first_name": "Andréa",
					"updateOn": "04/08/2020",
					"other_name": "Joan",
					"username": "aclark",
					"gender": "U",
					"addresses": [
							{
								"mobile2": "0412016500",
								"townSub": "TOOWONG",
								"parentType": "TER",
								"homePhone": "3870 9987",
								"email": "alec.heath@tassweb.com",
								"f_preferred_name": "Paula",
								"commtypeTk": "Y",
								"m_preferred_name": "Paula",
								"country": "",
								"stateCode": "QLD",
								"salutation": "Mr and Mrs Clark test",
								"personPosition": "",
								"m_suffix": "MA",
								"f_suffix": "MA",
								"fatherName": "Edward Other Clark",
								"addressDescription": "Postal",
								"mobile1": "0434542770",
								"reltagCode": "",
								"commtypeAca": "N",
								"f_initials": "P",
								"addressNumber": 1,
								"f_description": "Father/Parent 2",
								"f_other_name": "Other",
								"email2": "email2CorrClark2@tassweb.com.au",
								"f_title": "Ms",
								"commtypeTkcoDesc": "Teacher Kiosk Correspondence",
								"commtypeAcaDesc": "Academic Reports",
								"positionLabel": "",
								"m_description": "Mother/Parent 1",
								"m_other_name": "Other",
								"m_surname": "Clark",
								"businessPhone": "3201 1302",
								"parentName2": "",
								"commtypeAtt": "N",
								"postCode": 4066,
								"m_initials": "P",
								"commtypeTkco": "N",
								"parentCode": "000055",
								"smsFlag2": "Y",
								"smsFlag1": "N",
								"commtypeTkDesc": "Teacher Kiosk View",
								"parentName": "Mrs E Clark and the lesser Clarks for the giant wombock trees",
								"commtypeEc": "N",
								"m_title": "Ms",
								"commtypeGenDesc": "TASS.web Correspondence",
								"address1": "Gigi Lodge \"Shelta\"",
								"f_surname": "Clark",
								"address3": "",
								"address2": "24 Augustus 'Street'",
								"surname": "Clark",
								"commtypeLw": "N",
								"commtypeAttDesc": "Attendance",
								"commtypeEcDesc": "Emergency Contact",
								"m_first_name": "Paula",
								"dpidText": "",
								"reltagDescription": "",
								"commtypeGen": "N",
								"motherName": "Paula Other Clark",
								"f_first_name": "Paula",
								"fax": "375575756576",
								"commtypeLwDesc": "Student Lives With"
							}
					],
					"birthday": "02/09/1994",
					"rollClass": "F"
			},
			"__tassversion": "01.053.3.138",
			"token": {
					"commtype": "TK",
					"timestamp": "{ts '2021-01-20 16:02:31'}",
					"userid": "0009130"
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
