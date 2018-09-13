**getUser**
----
  Returns the specified User.

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
	user: {
		dateOfExpiry: "",
		surname: "Clark",
		mobilePhone: "0439443653 ",
		scholasticYear: 9,
		preferredName: "Lauren",
		emailAddress: "clark@tassweb.com.au",
		ceider: "8",
		firstName: "Lauren Jane",
		dateOfLeaving: "",
		updateOn: "04/12/2017",
		username: "0009134",
		currentStatus: "current",
		gender: "F",
		addresses: [
			{
				mobile2: "0416835939",
				postCode: 4005,
				townSub: "ALBION",
				parentType: "TER",
				commtypeTkco: "N",
				email: "paripper@bigpond.com; peterr@tassweb.com.au",
				homePhone: "3870 9987",
				parentCode: "000055",
				smsFlag2: "Y",
				smsFlag1: "N",
				commtypeTk: "Y",
				country: "AUSTRALIA",
				stateCode: "QLD",
				commtypeTkDesc: "Teacher Kiosk View",
				parentName: "Mrs E Clark",
				salutation: "Mr and Mrs Clark",
				personPosition: "",
				commtypeEc: "N",
				fatherName: "Edward Clark",
				commtypeGenDesc: "TASS.web Correspondence",
				address1: "Updated Correspondance Address",
				addressDescription: "Correspondence",
				mobile1: "0488067672",
				address3: "Addr Line 3",
				reltagCode: "",
				commtypeAca: "N",
				address2: "123 Smith Rd",
				surname: "Clark",
				commtypeLw: "N",
				addressNumber: 1,
				commtypeAttDesc: "Attendance",
				commtypeEcDesc: "Emergency Contact",
				dpidText: "",
				reltagDescription: "",
				commtypeGen: "N",
				commtypeTkcoDesc: "Teacher Kiosk Correspondence",
				commtypeAcaDesc: "Academic Reports",
				motherName: "Paula Clark",
				positionLabel: "",
				businessPhone: "3201 1302",
				fax: "375575756576",
				parentName2: "This is a second Line",
				commtypeAtt: "N",
				commtypeLwDesc: "Student Lives With"
			}
		],
		birthday: "02/09/1994",
		rollClass: "A"
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
	userid=0009134&type=S&commtype=TK
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
