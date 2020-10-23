**getStudentPhoto**
----
  Returns a Photo of a specified Student.
  
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

   `stud_code [string]` - Student Code
   
   **Optional:**
 
   `thumbnail [boolean]` - Returns a thumbnail instead of full size photo

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
	file_info: {
			image: [Base64 encoded image string],
			file_name: "0009068.jpg",
			mime_type: "image/jpeg"
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
		"userid":"0009068"
	}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getStudentPhoto&appcode=API07&company=10&v=3&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getStudentPhoto">
	  <input type="hidden" name="appcode" value="API07">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="3">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
