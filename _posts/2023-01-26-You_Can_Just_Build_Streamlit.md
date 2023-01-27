---
title: You can just turn data scripts into apps!
date: 2023-01-13 00:00:00 
categories: [Programming]
tags: [python, opensource, streamlit]
---

Ah, te voilà! Ever wondered if you can build apps with just a few lines of script/lines of codes. This is where **Streamlit** comes into play!

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

![Streamlit_homepage.png](./assets/media/streamlit-server.png)

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

[![rickandmorty_page.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658049949764/n6dPZawmt.png align="left")](https://dotaadarsh-30daysofstreamlit-miscrickandmorty-k6x6ey.streamlitapp.com/)

Live demo of our app - [OOH WEE!](https://dotaadarsh-30daysofstreamlit-miscrickandmorty-k6x6ey.streamlitapp.com/)

Try experimenting around and build whatever you want.

Need inspiration? Check out what creators from around the world are building - [Streamlit Gallery](https://streamlit.io/gallery)

## Deployment

* Add your app to GitHub
    
* Sign up for [Streamlit Cloud](https://share.streamlit.io/signup) \[with GitHub recommended\]
    

![Sign up for Streamlit Cloud.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658039402699/jC-mF0lV_.png align="left")

* Log in to share.streamlit.io
    
* Once you have signed in to GitHub, you will be taken to your Streamlit Cloud workspace!
    

![Streamlit Cloud workspace.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658039520375/E1JkfyLM_.png align="left")

* To deploy an app, click "New app", then fill in your repo, branch, and file path, or click "Paste GitHub URL" and click "Deploy".
    

![deploy_your_app.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658039811970/TFP2xbo_b.png align="left")

* You can now watch your app deploy and launch.
    

![deploy_manager.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658040189516/TPRXc9LN7.png align="left")

And that's it! Your app is live now; just like this [live demo](https://dotaadarsh-30daysofstreamlit-miscrickandmorty-k6x6ey.streamlitapp.com/) and you can share it with others.

# Resources 📚

* I suggest you try the **#30DaysOfStreamlit** challenge to challenge yourself to learn this wonderful framework - [Get started now](https://share.streamlit.io/streamlit/30days)
    
* Check out their wonderful [documentation](https://docs.streamlit.io/)
    
* [YouTube](https://youtube.com/playlist?list=PLtqF5YXg7GLmCvTswG32NqQypOuYkPRUE) Videos by [data professor](https://twitter.com/thedataprof/)
    
* [Shorts by Streamlit](https://youtube.com/playlist?list=PLgkF0qak9G4-TC9_tKW1V4GRcJ9cdmnlx)
    

# Conclusion

There are many more possibilities with Streamlit. For example, you can use it to build data exploration apps, dashboard apps, and even games.

Recently Streamlit has launched [multipage apps](https://blog.streamlit.io/introducing-multipage-apps/) 📄 and Dashboard analytics 📊. It's been evolving so quickly and gaining a lot of popularity among open-source developers. So what are you waiting for? Start building with Streamlit!

![sdsf](https://c.tenor.com/ErMSuHlcE8IAAAAi/clown-it.gif align="left")

Happy Streamlit-ing 🎈

And that's a wrap. Thanks for reading and don't forget to share your feedback. You can find me on Twitter - [Aadarsh Kannan](https://twitter.com/dotaadarsh). Stay tuned for more!

Stay safe 😷 Spread Love ❤️ and Keep Exploring 🚀