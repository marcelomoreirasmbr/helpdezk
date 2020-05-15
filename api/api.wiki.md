# Get all requests 

**/api/user/requests**
----
  Returns all uer's requests.

* **URL**

  http://helpdezk_url/api/user/requests

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
    Param | Description| Type
    ------------ | ------------- | --------
    token | Authentication token  | string

    **Optional:**

    Param | Description| Type
    ------------ | ------------- | --------
    token | Authentication token  | string
    idStatus | Request Status ["ALL" to all status] | string
    page | Page Number  | string
    sortName | Name to sort  | string
    sortOrder | Order to sort [ASC or DESC]  | string
    limit | Page limit  | int

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    Param | Description| Type
    ------------ | ------------- | --------
    token| Authorization token  | string
    id| User id  | int
    name | User name | string
    email | User email| string
    Status | Active or Inactive | String
    phone_number |  User phone number | string
    cel_phone| User cell phone | string
    company | User´s company | string
    city | City | string
    state | State | string
    state_abbr | State abbreviation | string
    country| Country  | string

    Example:

    ```json
    {
      "result": {
        "rows": {
          "page": "1",
          "total_pages": 571,
          "records_per_page": "2",
          "total_records": "1141",
          "records": [
            {
              "code_request": "202004000006",
              "entry_date": "2020-04-22 10:30:00",
              "subject": "Make menu config.",
              "expire_date": "04/24/2020 10:30 AM",
              "in_charge": "Roger Garcia Mendes"
            },
            {
              "code_request": "202004000002",
              "entry_date": "2020-04-08 11:35:00",
              "subject": "Printer network error.",
              "expire_date": "04/10/2020 11:35 AM",
              "in_charge": "Roger Garcia Mendes"
            }
          ]
        }
      }
    }
    ```
    

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** 
    ```json5
    {
        "result": {
            "error": "Error message."
        }
    }
    ```

    Example:

    ```json5
    {
        "result": {
            "error": "Invalid stautus Id."
        }
    }
    ```
  