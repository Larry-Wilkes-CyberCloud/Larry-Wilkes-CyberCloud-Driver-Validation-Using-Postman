<div>
  <h2>QA Engineer Portfolio: Driver Validation API</h2>
  <p><strong>Company:</strong> General Insurance INC. (Fictional)</p>
  <p>
    As a Quality Assurance Engineer at General Insurance INC., I tested and validated the Driver Validation API. Below are the results of the key test cases executed to ensure the API's robustness and reliability.
  </p>

  <h3>Test Case Outline:</h3>
  <ol>
    <li><strong>Test Case ID: TC01</strong> - Verify the successful creation of a driver record with all required and optional fields provided with valid data.</li>
    <li><strong>Test Case ID: TC02</strong> - Verify the system's response when attempting to create a driver record with a duplicated SSN, which should be unique.</li>
    <li><strong>Test Case ID: TC03</strong> - Verify that the API properly handles and rejects creation when a mandatory field (e.g., 'lastname') is missing.</li>
    <li><strong>Test Case ID: TC04</strong> - Verify the system's response when a non-existent driver ID is queried.</li>
    <li><strong>Test Case ID: TC05</strong> - Test the API's ability to handle invalid date formats in fields like 'dob'. Valid formats: YYYY-MM-DD, YY/MM/DD.</li>
  </ol>
  
  <h3>Test Case Results:</h3>
  
  <!-- Test Case 1 -->
  <table border="1">
    <thead>
      <tr>
        <th colspan="4">Test Case ID: TC01</th>
      </tr>
      <tr>
        <th>API Body</th>
        <th>Expected Result</th>
        <th>Actual Result</th>
        <th>Status Code</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          {
            "firstname": "Alice",
            "lastname": "Johnson",
            "dob": "1985-04-12",
            "email": "alice_johnson@example.com",
            "ssn": "255-45-6789",
            "phonenumber": "312-555-1234",
            "cellnumber": "312-555-5678",
            "createddate": "2023-07-10",
            "active": true,
            "isprimarypolicyholder": true,
            "policy_id": 98765432,
            "licenseissuedate": "2003-04-12",
            "licenseissuestate": "Illinois",
            "maritalstatus": "married"
          }
        </td>
        <td>API returns a success status with a message confirming the creation and the ID of the new driver record.</td>
        <td>I verified that the API returned a success status with a message confirming the creation and the ID of the new driver record.</td>
        <td>Status code 201 received.</td>
      </tr>
      <tr>
        <td colspan="4"><img src="https://github.com/Larry-Wilkes-CyberCloud/Larry-Wilkes-CyberCloud-Driver-Validation-Using-Postman-/assets/93053015/5e400a5f-a1b1-46af-ada3-79803725198a" width="1000" height="500"></td>
      </tr>
    </tbody>
  </table>
  <br>
  
  <!-- Test Case 2 -->
  <table border="1">
    <thead>
      <tr>
        <th colspan="4">Test Case ID: TC02</th>
      </tr>
      <tr>
        <th>API Body</th>
        <th>Expected Result</th>
        <th>Actual Result</th>
        <th>Status Code</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          {
            "firstname": "Bob",
            "lastname": "Smith",
            "dob": "1988-08-15",
            "email": "bob_smith@example.com",
            "ssn": "255-45-6789",
            "licenseissuestate": "Illinois"
          }
        </td>
        <td>API returns an error status and a message indicating that the SSN already exists.</td>
        <td>I verified that the API returned an error status and a message indicating that the SSN already exists.</td>
        <td>Status code 400 received.</td>
      </tr>
      <tr>
        <td colspan="4"><img src="https://github.com/Larry-Wilkes-CyberCloud/Larry-Wilkes-CyberCloud-Driver-Validation-Using-Postman-/assets/93053015/e7b7722b-0dad-4b3e-b0fa-87133d9eccd7" width="1000" height="500"></td>
      </tr>
    </tbody>
  </table>
  <br>
  
  <!-- Test Case 3 -->
  <table border="1">
    <thead>
      <tr>
        <th colspan="4">Test Case ID: TC03</th>
      </tr>
      <tr>
        <th>API Body</th>
        <th>Expected Result</th>
        <th>Actual Result</th>
        <th>Status Code</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          {
            "firstname": "Carol",
            "email": "carol@example.com",
            "ssn": "987-65-4321",
            "licenseissuestate": "Illinois"
          }
        </td>
        <td>API returns an error status with a message indicating that the 'lastname' field is required but was not provided</td>
        <td>I verified that the API returned an error status with a message indicating that the 'lastname' field is required but was not provided</td>
        <td>Status code 400 received.</td>
      </tr>
      <tr>
        <td colspan="4"><img src="https://github.com/Larry-Wilkes-CyberCloud/Larry-Wilkes-CyberCloud-Driver-Validation-Using-Postman-/assets/93053015/c2c3deda-1f8d-45a0-978d-2096a9326704" width="1000" height="500"></td>
      </tr>
    </tbody>
  </table>
  <br>
  
  <!-- Test Case 4 -->
  <table border="1">
    <thead>
      <tr>
        <th colspan="4">Test Case ID: TC04</th>
      </tr>
      <tr>
        <th>API Body</th>
        <th>Expected Result</th>
        <th>Actual Result</th>
        <th>Status Code</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>(Query operation) /driver/999999 GET Request</td>
        <td>API returns an error status and a message indicating that the driver ID does not exist.</td>
        <td>I verified that the API returned an error status and a message indicating that the driver ID does not exist.</td>
        <td>Status code 404 received.</td>
      </tr>
      <tr>
        <td colspan="4"><img src="https://github.com/Larry-Wilkes-CyberCloud/Larry-Wilkes-CyberCloud-Driver-Validation-Using-Postman-/assets/93053015/5c6cf330-5827-4a37-85a4-0e47d6db04e1" width="1000" height="500"></td>
      </tr>
    </tbody>
  </table>
  <br>
  
  <!-- Test Case 5 -->
  <table border="1">
    <thead>
      <tr>
        <th colspan="4">Test Case ID: TC05</th>
      </tr>
      <tr>
        <th>API Body</th>
        <th>Expected Result</th>
        <th>Actual Result</th>
        <th>Status Code</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          {
            "firstname": "Diana",
            "lastname": "Ross",
            "dob": "12-31-1980",
            "email": "diana_ross@example.com",
            "ssn": "321-54-6789",
            "phonenumber": "312-555-4321",
            "cellnumber": "312-555-6789",
            "createddate": "2023-07-10",
            "active": true,
            "isprimarypolicyholder": true,
            "policy_id": 65432109,
            "licenseissuedate": "2000-12-15",
            "licenseissuestate": "California",
            "maritalstatus": "single"
          }
        </td>
        <td>API returns an error status and a message detailing the incorrect date format, specifying the expected format.</td>
        <td>API did not return an error status and a message detailing the incorrect date format, specifying the expected format. This Endpoint has a Defect. Will report issue.</td>
        <td>Status code 201 received.</td>
     

 </tr>
      <tr>
        <td colspan="4"><img src="https://github.com/Larry-Wilkes-CyberCloud/Larry-Wilkes-CyberCloud-Driver-Validation-Using-Postman-/assets/93053015/f92f9427-593c-434e-97d5-552050855d09" width="1000" height="500"></td>
      </tr>
    </tbody>
  </table>
  <br>
</div>
