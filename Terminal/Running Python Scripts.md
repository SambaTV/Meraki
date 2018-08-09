# First Set up Text editor

  1. Open a text editor 
  ex) Sublime
  
  2. Create a file
  
  3. Copy and paste this into the file:
  
          import requests
          import json

          api_key = "<YourAPIKey>"
          url = "https://{}:x@api.bamboohr.com/api/gateway.php/sambatv/v1/employees/directory".format(api_key)
          header = {"Accept": "application/json"}
          response = requests.get(url,headers=header)
          response_data = json.loads(response.content)
          print response_data
  
      
  4. Click Save file As and create a name for your file with with .py at the end
  ex) LastChangeInformation.py
  
# Then Set up Terminal

  5. open a Terminal 
  
  6. create a path to the file using cd
          
          cd Downloads
          cd Meraki\ BambooHR\ PY/
          
  7. Enter python, then file name
  
          python LastChangeInformation.py
          
  8. run scripts inside
