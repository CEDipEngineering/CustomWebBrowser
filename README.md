# CustomWebBrowser
Using NLP and WebScraping, build a database of indexed web pages which can be searched using a simple flask based web interface.

# To run

First run webscraper with the proper mysql configurations in place. This assumes you have mysqld server running and open on localhost 
(can be external network too, with proper configuration and authentication should work fine) with a table called Pages, that has 4 columns, id (int Auto Increment Primary Key Not null)
url (TEXT not null), title (TEXT not null), content (TEXT not null). WARNING, this can take a long time, anywhere from 2 to 3 hours, depending the depth and url you provide as inputs.

After running scraper, run the other notebook (parser.ipynb) to build the other two tables Words (similar to Pages, has column id, and column word) 
and Words_To_Pages (id_Word, id_Page, tf_idf), which is a relation table between the other two.

Finally, from the root of the repository, run "$ flask run" will start the web service on port 5000 on you localhost.
