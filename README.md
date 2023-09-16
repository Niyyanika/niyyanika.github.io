# niyyanika.github.io

Goal: Create an ontology (data model) of Vinaya concepts and metadata 
that can be populated with information from across Vinaya texts from multiple Buddhist Vinaya holding traditions, 
with translations and information about the Vinaya texts, concepts, and translations 
so that the information can be queried, reasoned about, and further elucidated
for the benefit of supporting monastics and their practice in the world. 

"The idea for the website is to have reusable components that are rendered based on the user's query."

React is ideal for this and it is one of the reasons the library was ever developed, especially in order to prevent having to constantly reload the entire DOM. If your goal is to create a SPA (single page application), React is a good choice.

"I have only done a rough mockup of some of the returned data in a Google slide deck and only a spreadsheet representation of the query (just so we had an idea of what was needed to query, not at all on how the query page should look.)"

Looking over your slides and query mockups, as well as the frontend draft, I would say that what you are looking to do is very much feasible, but will certainly be a project.

I am not sure which backend technologies you are using-- I did look over your Ontology and Data Source files, and it looks like you have a class-based database system going on to organize your data sources. I probably wouldn't be much help for the backend side of things, but the good news is that there are a dozen technologies that help backend and frontend talk to each other- JSON is a popular one that React has a whole library for working with. As long as your data can be standardized in an object, which should be possible for basically any set of text, then it ought to be quite doable.

In terms of your frontend design draft-- it's certainly feasible. What you would probably be aiming to do is create some components that display information, some components that handle opening/closing the dropdown window, components for providing access to a search function, and so on. You will want to use good separation of concerns, including separating out your container components (that do the processing) from your presentational components (that handle how things are displayed). You also will need to utilize a lot of state management, but if you are good about separating out your components into logical pieces, you should be able to keep track of your states pretty well.

As to the search itself, that's going to combine frontend and backend, but ultimately you're probably going to be receiving a lot of data that should be formatted into JSON or another standardized form, and from there you can have components that receive imported props from parent components and you can use JSX and object destructuring to pull out the information that you need so your component, when it's actually passed into your root to be rendered, might look something like:

<DisplayText school={school} language={language} bhikPrefix={bhikPrefix} text={text} ruleClass={ruleClass} />

With each of those JSX calls being a prop coming in from the imported data (or, perhaps, a function that returns the relevant value- either could work).

Anyway, those are just my initial thoughts. I don't know how much help they will be-- as I said I am still very much learning myself, but I definitely think your project is doable with React and a compatible backend stack.
