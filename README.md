# Building-a-URL-Shortener-with-Python
Building a URL Shortener with Python


# Building a URL Shortener with Python

## Introduction

URL shorteners are widely used to convert long web addresses into short and easy-to-share links. Popular services such as Bitly and TinyURL use this concept to improve readability and link management.

In this project, we will create a simple URL shortener using Python. The application generates a unique short code for each URL and stores it in memory.

## Features

* Shorten long URLs
* Generate unique short codes
* Retrieve original URLs
* Beginner-friendly code

## Source Code

```python
import random
import string

url_database = {}

def generate_code(length=6):
    characters = string.ascii_letters + string.digits
    return ''.join(random.choice(characters) for _ in range(length))

def shorten_url(url):
    code = generate_code()
    url_database[code] = url
    return f"https://short.ly/{code}"

def get_original_url(code):
    return url_database.get(code, "URL not found")

# Example
url = "https://www.example.com/very/long/url"
short_url = shorten_url(url)

print("Original URL:", url)
print("Short URL:", short_url)

code = short_url.split("/")[-1]
print("Recovered URL:", get_original_url(code))
```

## Example Output

```text
Original URL: https://www.example.com/very/long/url

Short URL: https://short.ly/aB3xK9

Recovered URL: https://www.example.com/very/long/url
```

## How It Works

The program generates a random code using letters and numbers. The code becomes the short link identifier and is mapped to the original URL. When a user enters the code, the application retrieves the corresponding URL.

## Future Improvements

* Store URLs in SQLite
* Create a web interface with Flask
* Add click analytics
* Generate QR Codes
* User authentication

## License

MIT License
