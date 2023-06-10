---
title: You can just turn data scripts into apps!
date: 2023-01-13 00:00:00 
categories: [Technology, Development]
tags: [data scripts, apps]
---

Ah, te voilà! Ever wondered if you can build apps with just a few lines of script/lines of codes. This is where **Streamlit** comes into play!

![Streamlit](https://community.codenewbie.org/images/TSu5D2bPkxaCjUfhGsdsnvuklypQL7uBFUuMfotxZcE/s:1000:420/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkuY29kZW5l/d2JpZS5vcmcvcmVt/b3RlaW1hZ2VzL3Vw/bG9hZHMvYXJ0aWNs/ZXMvd3N3eW4ybnhv/NnF0cHE5djBkM2ou/anBn)

# About streamlit

[**Streamlit**](https://streamlit.io/) is an open-source app framework for Machine Learning and data science. It is based on the idea that the best way to learn and use new tools is not through tutorial articles or videos, but by exploring working examples.

In other words, Streamlit is designed to let you build apps for your Machine Learning projects without having to learn a new framework or language. In just a few minutes, you can build an interactive app that lets you explore a dataset, visualize results, and even share your app with others. All you need is **basic Python knowledge and a web browser**.

Streamlit is built by a team of engineers and data science enthusiasts at Streamlit Inc., a startup based in San Francisco, CA. It is also lightweight and fast. The apps you build with it can be deployed easily on any platform, including Heroku and AWS.

# Get Started

Open the terminal from wherever you want to and run the below commands.

```shell
pip install streamlit
```

```shell
streamlit hello
```

You will be able to see the page as shown below!

![Streamlit_homepage.png](https://community.codenewbie.org/images/1fzfnMXHejdh5leS1_qgBKZe5oBc0Ke57Z6JP0dV_18/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvcGYw/NXo2dmRid3o2cjBm/aHpqN3AucG5n)

And that's it boom! you are done setting up the framework! Now we can start building whatever the hell we want.

## Let's built an app with some basic elements

Create a .py file - This is where we will be writing our code for the app.

First, let's import the streamlit module

```python
import streamlit as st
```

For this tutorial, let's built a basic page based on Rick and Morty. Below are the codes which you will be able to understand easily. Let's code it out!

```python
# Display text in title formatting
st.title("OOH WEE!")
```

```python
# Display text in header and subheader formatting
st.header("Rick and Morty")
st.subheader("American adult animated science fiction sitcom")
```

```python
# Display an image or list of images
st.image("https://upload.wikimedia.org/wikipedia/commons/9/9e/Rick_and_Morty_title_card.png", caption = "Justin Roiland and Dan Harmon, Public domain, via Wikimedia Commons")
```

```python
# Write arguments to the app
st.write('**Rick and Morty** is one of the best animated series on television. The show is about the adventures of Rick, a mad scientist, and his grandson, Morty. The series is hilarious and has a lot of heart.')
```

```python
# Display a code block
code = '''def rick():
     print("Boom! Big reveal! I turned myself into a code block")'''

st.code(code, language='python')
```

```python
# Display a button widget
if st.button("Just don't click this button"):
     st.image('https://c.tenor.com/5IFS2BehSGUAAAAC/morty-you-dirty-little-doggy.gif')
```

```python
# Display a slider widget
dimension = st.slider('Select your dimension', 0, 200, 137)
st.write("I'm from C-", dimension, ' dimension')
```

```python
# Display a select widget
fav = st.selectbox(
     'Who is your favourite character?',
     ('Rick Sanchez', 'Morty Smith', 'Birdperson', 'Summer Smith', 'Mr. Poopybutthole'))
```

```python
# Display an informational message
st.info('Nobody exists on purpose. Nobody belongs anywhere. We are all going to die. Come lets built apps with Streamlit')
```

Below is the complete code of our basic app.

```python
import streamlit as st

st.title("OOH WEE!")

st.header("Rick and Morty")

st.subheader("American adult animated science fiction sitcom")

st.image("https://upload.wikimedia.org/wikipedia/commons/9/9e/Rick_and_Morty_title_card.png", caption = "Justin Roiland and Dan Harmon, Public domain, via Wikimedia Commons")

st.write('**Rick and Morty** is one of the best animated series on television. The show is about the adventures of Rick, a mad scientist, and his grandson, Morty. The series is hilarious and has a lot of heart.')

code = '''def rick():
     print("Boom! Big reveal! I turned myself into a code block")'''

st.code(code, language='python')

if st.button("Just don't click this button"):
     st.image('https://c.tenor.com/5IFS2BehSGUAAAAC/morty-you-dirty-little-doggy.gif')

dimension = st.slider('Select your dimension', 0, 200, 137)
st.write("I'm from C-", dimension, ' dimension')

fav = st.selectbox(
     'Who is your favourite character?',
     ('Rick Sanchez', 'Morty Smith', 'Birdperson', 'Summer Smith', 'Mr. Poopybutthole'))

st.write('You favourite character is ', fav)

st.info('Nobody exists on purpose. Nobody belongs anywhere. We are all going to die. Come lets built apps with Streamlit')
```

Once you've created your script, say [rickandmorty.py](https://raw.githubusercontent.com/dotaadarsh/30DaysOfStreamlit/main/Misc/rickandmorty.py), the easiest way to run it is with streamlit run:

```python
$ streamlit run rickandmorty.py
```

Once you run the script, you will be able to see a tab in your browser. You can run this in the beginning and build your app by visualizing each element. This will help you understand quickly.

![rickandmorty_page.png](https://community.codenewbie.org/images/fiT17x8u28llv-9Xx8BM5_I-H2-wmqnG-nxlUNcE3-k/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvdG53/ZjZsdnN6ZjlsOGVr/bHpwbnoucG5n)

Try experimenting around and build whatever you want.

Need inspiration? Check out what creators from around the world are building - [Streamlit Gallery](https://streamlit.io/gallery)

## Deployment

* Add your app to GitHub
    
* Sign up for [Streamlit Cloud](https://share.streamlit.io/signup) \[with GitHub recommended\]
    

![Sign up for Streamlit Cloud.png](https://community.codenewbie.org/images/z4e0o55oW1rNLUaEDFYh1mwHRpNqZJxBsOoq6xtNn2w/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvYjR4/bm5tbGQwbG5rempk/MnVhdjAucG5n)

* Log in to share.streamlit.io
    
* Once you have signed in to GitHub, you will be taken to your Streamlit Cloud workspace!
    

![Streamlit Cloud workspace.png](https://community.codenewbie.org/images/IMnsJJH4G-qhqSHdSh5GiFRBwzk3M6MX7t05OETwxwg/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvdWpv/MnI3eWZyb2FiY3Y0/bGZkcTQucG5n)

* To deploy an app, click "New app", then fill in your repo, branch, and file path, or click "Paste GitHub URL" and click "Deploy".


![deploy_your_app.png](https://community.codenewbie.org/images/AIaJMqCruMJhEa6IXopu4735KgZa_tQ9fJW7SU8PaXU/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvMnBm/YmkycjVlZmFnOXEx/YWFveGoucG5n)

* You can now watch your app deploy and launch.
    

![deploy_manager.png](https://community.codenewbie.org/images/GuhX1xhmIys2VONfD70CXQb6iirB0bT5FwdhA_0C9GE/w:880/mb:500000/ar:1/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvd2M0/dTA4Zzhldm11MmIz/eGVybmsucG5n)

And that's it! Your app is live now and you can share it with others.

# Resources 📚

* I suggest you try the **#30DaysOfStreamlit** challenge to challenge yourself to learn this wonderful framework - [Get started now](https://share.streamlit.io/streamlit/30days)
    
* Check out their wonderful [documentation](https://docs.streamlit.io/)
    
* [YouTube](https://youtube.com/playlist?list=PLtqF5YXg7GLmCvTswG32NqQypOuYkPRUE) Videos by [data professor](https://twitter.com/thedataprof/)
    
* [Shorts by Streamlit](https://youtube.com/playlist?list=PLgkF0qak9G4-TC9_tKW1V4GRcJ9cdmnlx)
    

# Conclusion

There are many more possibilities with Streamlit. For example, you can use it to build data exploration apps, dashboard apps, and even games.

Recently Streamlit has launched [multipage apps](https://blog.streamlit.io/introducing-multipage-apps/) 📄 and Dashboard analytics 📊. It's been evolving so quickly and gaining a lot of popularity among open-source developers. So what are you waiting for? Start building with Streamlit!

![balloon](https://c.tenor.com/ErMSuHlcE8IAAAAi/clown-it.gif align="left")

Happy Streamlit-ing 🎈

And that's a wrap. Thanks for reading and don't forget to share your feedback. You can find me on Twitter - [Aadarsh Kannan](https://twitter.com/dotaadarsh). Stay tuned for more!

Stay safe 😷 Spread Love ❤️ and Keep Exploring 🚀