**getEmployee**
----
  Returns the specified Employee.
  
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
 
   `userid [string]`

   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
	{
		"__status":"success",
		"__tassversion":"01.000.043.0",
		"__invalid":{},
		"__locks":{},
		"user":{
			"mobPhone":"0488067672",
			"nokAdd2Text":"Bramwell Heights",
			"positionTitle":"Head of Senior School",
			"startDate":"04/09/2000",
			"postCode":4170,
			"nokPostCode":4170,
			"nokNameTest":"Amanda Johnson",
			"add1Text":"12 Holt St",
			"email":"bill.jiang@tassweb.com.au",
			"initialsText":"A",
			"stateText":"QLD",
			"currentStatus":"current",
			"schoolEmail":"peter.pumpkin@tassweb.com.au",
			"supervisor2Code":"",
			"tchCode":"AJ",
			"salutationFlag":"Mr",
			"nokCountryText":"AUSTRALIA",
			"phoneHText":"3899 4190",
			"givenNamesText":"Alan Pierre",
			"username":"ajohnstone",
			"isTeacher":true,
			"preferNameText":"Alanx",
			"id":1000016,
			"nokCityText":"CANNON HILL",
			"statusText":"F",
			"nokPhoneHText":"3899 4190  mob 0427 776 116",
			"termDate":"",
			"cityText":"CANNON HILL",
			"nokPhoneWText":"3217 6654",
			"positionText":"Teacher",
			"nameSuffix":"BA, DipTch (MIT), QCT",
			"dpidText":"",
			"sexFlag":"M",
			"smsFlg":"Y",
			"empCode":1000016,
			"nokrelatText":"Wife",
			"phoneWText":38970111,
			"supervisorCode":"",
			"surnameText":"O'Johnstonex",
			"add2Text":"Up the road",
			"nokAdd1Text":"10 Holt Street",
			"countryText":"",
			"superNoText":"",
			"nokStateText":"QLD",
			"tchName":"Mr A Johnstone"
		},
		"token":{
			"timestamp":"{ts '2020-10-12 08:44:55'}",
			"userid":1000016,
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
	
* **Sample Parameters:**

  ```javascript
	{
		'userid':'1000016'
	}
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
