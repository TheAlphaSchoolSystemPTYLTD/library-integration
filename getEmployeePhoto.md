**getEmployeePhoto**
----
  Returns a Photo of a specified Employee.
  
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

   `emp_code [string]` - Employee Code
   
   **Optional:**
 
   `thumbnail [boolean]` - Returns a thumbnail instead of full size photo

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
		{
			"file_info": {
					"image": "[Base64 encoded image string]",
					"file_name": "Unavailable.gif",
					"mime_type": "image/gif"
			},
			"__tassversion": "01.053.3.000",
			"token": {
					"timestamp": "{ts '2021-01-20 15:58:13'}",
					"emp_code": 1000016,
					"type": "E"
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
	
	`thumbnail` not a boolean
	```javascript
	__invalid: {
	  "thumbnail": "'thumbnail' must be true or false."
	}
	```

* **Sample Parameters:**

  ```javascript
	{
		"emp_code":"1000016"
	}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getEmployeePhoto&appcode=API07&company=10&v=3&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getEmployeePhoto">
	  <input type="hidden" name="appcode" value="API07">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="3">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
