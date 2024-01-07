# get_info
GitHub repository using python

def say_hello(name: str, repeat: int=1, goodbye: bool = False) -> None:


  if goodbye:
      message = 'Goodbye'
  else:
      message = 'Hello'

  for _ in range(repeat):
      print(f'{message} {name}!')
#______________________________________________________________________________________________________________________


say_hello('World', 3, True)

import requests
import json
from pprint import pprint

# get secret from Colab
from google.colab import userdata
token = userdata.get('ghtoken')

# initialize request parameters
url = 'https://api.github.com/user'
headers = {'Authorization': 'Bearer ' + token}

# send request to GitHub
r = requests.get(url, headers=headers)

# print initial responses
print(r.status_code)
print(r.text)
r_json = json.loads(r.text)
pprint(r_json)
