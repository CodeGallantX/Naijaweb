# naijaweb

Note: The webscraping was done on **google colab**, the google colab free memory plus the **easy google drive integration** made this easiy. The clean_download_data.ipynb, clean_download_data_403.ipynb, download_webpages.ipynb, webscrape_403.ipynb, webscrape_nairaland.ipynb files were run on 9 different notebooks (3 notebooks on 3 google colab accounts), to reduce the time it would have taken to run the files, although they were all linked to one drive folder ("/content/drive/MyDrive/nairaland_webtext") and all the files were saved in that folder.

Webscrape_nairaland.ipynb
This file webscrape and extract the posts in a particular section from Nairaland, the script downloads all the **links to the posts for each section** and saves them to a pickle file. Then eacch of the posts are downloaded, because of the limited runtime for ggogle colab, I had to create 9 different notebooks and I splitted the long list of the links to the posts into small chunks then I downloaded the, to make them faster.

extract_outboundlinks.ipynb
This file extract all the outbound links from the downloaded posts, filters off some websites, does some simple cleaning and saves them into a csv file.

download_webpages.ipynb
Thsi page downloads the webpages from the outbound links extracted from the previous file. It dowbloads the file in a batch of 1000 and saves them unto a pickle file. I ran this in 9 noteboks also because of time.

clean_download_data.ipynb
This file extract and cleans the downloaded pages using Trafilatura (inspired by the fineweb paper) and saves the cleaned files, webpages that gave a Forbidden response (403) bwere saved to be worked on later.

webscrape_403.ipynb
Webpages that returned a 403 response were redownloaded using cloudscraper.

clean_download_data_403.ipynb
The 403 redownloaded files were cleaned and extracted.

fineweb_clean_data.ipynb
The file applies the same cleaning doned on the pouplar fineweb dataset on the data. 
It fllows the following steps
🔻 - FILTER: 😈 Url-filter
🔻 - FILTER: 👯 Gopher Repetition
🔻 - FILTER: 🥇 Gopher Quality
🔻 - FILTER: ⛰ C4 Quality
🔻 - FILTER: 🍷 FineWeb Quality
🔢 - TOKENIZER: 📊 Counter
💽 - WRITER: 🐿 Jsonl

PII_formatter.ipynb
This removes Peronsal iodentifiabke information from the dataset, email and IP address.

push_to_hub.ipynb
This file pushes the full dataset to huggingface and calculates the educations score of the dataset, using the fineweb edu classifoer. The classifier predictions might not be as accurate because tjhe model **probably** wasnt trained on as much nigerian data.

extract_naijaweb_edu.ipynb

This file gets the language of the dataser anbd creates two subsrtsz rom thde datasets,**naijaweb edu** and **naijaweb edu2**, using the educational score, an attemot at recreating the fineweb edu dataset.







