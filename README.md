This project application is intended to operate as follows. The user pastes a URL link from the https://www.frontiersin.org/ scientific journal website, this link has to be of an original research paper ONLY. The user would then select what sort of information about the link they want to receive. Some examples include summaries of specific sections, text embedding that enables semantic search, pulling out figures combined with figure subtext and performance metrics of the paper (altmetric score, total views, dowloads and citations).

My aim with this project is to practice scalable web-scraping coding using Python by creating an application that may bring value to people such as researchers or students. My hope is to allow said demographic to parse through a large volume of papers, select specific papers using the application and focus on those papers. Effectively, I want to use the recent advances in natural language processing and machine learning to make paper search more efficient and allow for "current advances in {topic}" data easier to generate. 

Current Architecture

Classes:
1) Connect (connects to the link using the requests package)
2) Scrape (mainly using BeautifulSoup4 package this class scrapes text paragraph by paragraph, section by section)
3) Clean (cleans the text by eliminating html language and regex)

Methods:

-Connect
   1) request (request connection with given link)

-Scrape
   1) paper_type_new (identifies if the html format of the link is of the "newer" type, this has implication on the scraping class used further down the line)
   2) extract_abstract (extracts the abstract)
   3) extract_old (extracts text from "older" html format papers)
   4) section_looper (used in the extract_old method)
   5) extract_new (extracts text from "newer" html format papers)
   6) extract_new_ref (extracts the references text from "newer" html format papers)
   8) extract_new_foot (extracts the footer text from "newer" html format papers)
   9) extract_article_type (extracts the article type of the paper)
   10) section_number (number of h2 "main" sections in the paper)
   11) extract_image_links (extracts the links to images from the paper)

-Clean
   1) just_text (converts from html BeautifulSoup4 style objects into text and carries out additional cleaning using regex)

This project is in development meaning that more methods could be added or a resctructuring of the methods could take place. As well as the change in ideas or addition/substraction of currently proposed features.
