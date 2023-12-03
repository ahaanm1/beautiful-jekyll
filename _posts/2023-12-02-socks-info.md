---
layout: post
title: Lab 3 - Socks
subtitle: Analyzing Sock Data using APIs
cover-img: /assets/img/shutterstock_1697804203_0.jpg
thumbnail-img: /assets/img/eOiV-2uiH60YZtopuYpw3euERLpv6rj3rF6DqfYTkqM.jpg
share-img: /assets/img/shutterstock_1697804203_0.jpg
tags: [books, test]
---
## 1. Discuss how you used the API to obtain the dataset.

For this lab, I was given a dataset that I needed to obtain onto my console so that I can run code on it. The way to do this is the use of API's.

First, I needed to import the python package, requests, which allows me to work with API's. Python requests is a library for making HTTP requests and allows you to easily work with HTTP.
~~~
import requests
~~~
Then I needed to actually use the requests library to access the website.
~~~
url = "https://afeingoldhm.pythonanywhere.com/socks"
payload = {"key": "AhaanArtOfDataKEY123ABCsecret", "idx": i}
response = requests.get(url, params=payload)
~~~
Firstly, payload in this code has a key and an index. The key is a sort of "password" to get into the API. THe index is labeled as i and I refer to it in my for loop, but it is basically referring to each specific index in the API. The url part is getting the API to work with and specifying that we are working with the socks API. Finally, response is being assigned to the requests.get function has our url which specifies where to go, and the params=payload, which specifies how to get into the API.

## 2. Which sock has the most variations? If there is more than one answer, then list all of them.

My code outputed these socks for having the most variations:
- Sock Name: argyle crew socks
- Sock Name: color-blocked socks
- Sock Name: frilly knee-high socks
- Sock Name: holey tights
- Sock Name: kiddie socks
- Sock Name: mixed-tweed socks
- Sock Name: no-show socks
- Sock Name: semi-opaque socks
- Sock Name: semi-opaque tights
- Sock Name: sequin leggings
- Sock Name: simple-accent socks
- Sock Name: striped socks
- Sock Name: striped tights
- Sock Name: tube socks
- Sock Name: ultra no-show socks
- Sock Name: vivid leggings
- Sock Name: vivid socks
- Sock Name: vivid tights

These are all the types of socks that are tied for the most varitations(8). I thought about this for a while, trying to figure out how what exactly I needed to do. I then realized that if I simply find the variations at each index, I can loop through the big dictionary and add the variation to a new dictionary, which you can see below.
~~~
for idx, sock_info in sock_dict.items():
      sock_name = sock_info["name"]
      variation = (sock_info["color1"], sock_info["color2"])
    #loops through the socks and takes note of its name and variations

      if sock_name not in variations:
          variations[sock_name] = [variation]
      else:
          variations[sock_name].append(variation)
~~~
After, I had my dictionary of the variations I had to find which value occured most frequently, and print them out with this code.
~~~
  max_variations_count = max(len(variations_list) for variations_list in variations.values())
  most_variations_socks = [sock_name for sock_name, variations_list in variations.items() if len(variations_list) == max_variations_count]
  #finds the values of the dictionary and sees which occurs the most or is the longest

  print(f"The sock(s) with the most variations ({max_variations_count} variations):")
  for sock_name in most_variations_socks:
      print(f"- Sock Name: {sock_name}")
  #returns the sock_name everytime one with the most variations is found
  return variations
~~~

## 3 How many socks of each color are there? If a sock has two different colors, it should be counted in both. However, if a sock has the same Color1 and Color2, make sure you don’t double count it!

My code outputed this dictionary containing the colors and the times they appear
~~~
{'Pink': 44, 'Red': 43, 'Aqua': 33, 'Orange': 28, 'Purple': 39, 'Green': 51, 'Blue': 48, 'Yellow': 34, 'White': 89, 'Black': 65, 'Beige': 16, 'Gray': 33, 'Brown': 11, 'Colorful': 14}
~~~

For this question, I was stuck for a while. I knew the basis of what I needed to do but I was unsure how exactly I should code it. Eventually, I thought of a way to just use a series of if clauses to check if the colors match and if they do add it to a dictionary of key color and value being the number of times the color appears.

Firstly though, I looped through the keys and values of the dictionary and made the variables color1 and color2 to the colors from the API.
~~~
for idx, sock_info in sock_dict.items():
    color_1 = sock_info["color1"]
    color_2 = sock_info["color2"]
~~~
Then, I ran my series of if statements
~~~
if color_1 not in colors:
      colors[color_1] = 1
    #sees if the color isn't on the list already
    else:
      colors[color_1] += 1
    #if the color is already on the list, it adds one to the count
    if color_1 != color_2:
      #checks for duplicates
      if color_2 not in colors:
          colors[color_2] = 1
      else:
          colors[color_2] += 1
  print(colors)
~~~
This code prints the dictionary colors, which contains the the name of the color and the amount of times it appears. It also took in account for duplicates.

## 4.Discuss your process of how you worked on this lab. Include details such as who you worked with, what methods you tried, what worked or didn’t work, what could have gone better, and what you learned during this lab. Focus more on the programming side of the lab! Feel free to attach images, screenshots, pseudocode, etc to elaborate on your response.

This lab, overall, was very fun when my code worked but also extremely tedious. It was very annoying waiting almost 3-4 minutes for my code to run because it had to loop through 363 indexes. However, aside from that, the experience was good, and I think I learned as a coder. At first, I was a bit confused about what exactly API's did, so I asked Thomas about that, but afterwards, I mainly did all the coding myself. I did ask Yash a question about starting the colors function because I found that somewhat difficult to start as I mentioned above. I tried lots of different methods, some of which caused me to go back to my original code after trying to change my for loop to a while loop. Eventually, I decided my while loop was confusing me, so I went to my for loop and was able to work from there. I felt demotivated at point waiting all the time for the loop to run just to see an error. However, eventually my code ran and I felt accomplished. I learned a lot about working with API's and how to access them properly from this lab.


