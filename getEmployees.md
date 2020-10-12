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
		"__status":"success",
		"__tassversion":"01.000.043.0",
		"__invalid":{},
		"__locks":{},
		"users":[
			{
				"mobPhone":"0426 275 323",
				"nokAdd2Text":"",
				"positionTitle":"Title",
				"startDate":"11/05/1993",
				"postCode":4000,
				"nokPostCode":"",
				"nokNameTest":"Alli",
				"add1Text":"32 Giles Ct",
				"email":"N.Allibone@alphabus.com.au",
				"initialsText":"NC",
				"stateText":"QLD",
				"currentStatus":"current",
				"schoolEmail":"Nikola.Allibone@alphabus.com.aubnm",
				"supervisor2Code":"",
				"tchCode":"NA1",
				"salutationFlag":"Mr",
				"nokCountryText":"",
				"phoneHText":"07 3546 2041",
				"givenNamesText":"Nikola Craig",
				"username":"",
				"isTeacher":true,
				"preferNameText":"Niki",
				"id":1000066,
				"nokCityText":"",
				"statusText":"F",
				"nokPhoneHText":"",
				"termDate":"",
				"cityText":"MOUNT OMMANEY",
				"nokPhoneWText":"",
				"positionText":"Manager",
				"nameSuffix":"",
				"dpidText":"",
				"sexFlag":"M",
				"smsFlg":"N",
				"empCode":1000066,
				"nokrelatText":"",
				"phoneWText":"07 3542 2542",
				"supervisorCode":"",
				"surnameText":"Allibone",
				"add2Text":"",
				"nokAdd1Text":"",
				"countryText":"",
				"superNoText":"",
				"nokStateText":"",
				"tchName":"Mr N A'llibone"
			}
		],
		"token":{
			"timestamp":"{ts '2020-10-12 09:01:37'}",
			"currentstatus":"current",
			"type":"E"
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
	{
		'currentstatus':'current'
	}
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
