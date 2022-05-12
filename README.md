# Spam-Classifier
The idea of this project is to understand step by step working of the spam filter and how it helps in making everyone life easier. Also, next time when you see a “You have won a lottery” email rather than ignoring it, you might prefer to report it as a spam.  
![image](https://user-images.githubusercontent.com/89807104/168064080-da1ce94f-fa6e-47af-a5c7-984a6c03bb04.png)
The above image gives an overview of spam filtering , plenty of emails arrive everyday, some goes to spam and rest stays in our primary inbox(unless you have further categories defined). The blue box in the middle — Machine Learning Model, how does it decide which mail is spam and which one is not.

# Introduction
In machine learning point of view when we choose spam filtering approach, we can see classification problem. Here we classify email as spam or not spam (Ham) which depends on the features. But, in our point of view the features are the count of each word in the email. Training and Testing are the two modes which a machine learning system operates. In training the AI system is a given labelled data from the training data set. But in our project large set of emails are the labelled training data which is labeled spam or not spam (Ham). In the training process the classifiers prepare from the training data shows the interlink between the email and its label. But in the testing process an unlabeled data is given to the machine learning system. These data are the emails without the spam/ham label. The classifier in the testing shows us either it is spam or ham which depends on the features of an email.

Build a model to classify email as spam or ham. First, download examples of spam and ham from Apache SpamAssassin’s public datasets and then train a model to classify email.

# Steps involved to build Spam Classifier
Moving on to our aim of creating our very own spam detector. Let’s talk about about that blue box in the middle of above image. The model is like a small kid unless you tell the kid, the difference between salt and sugar, he/she won’t be able to recognize it. The similar idea we apply on machine learning model, we tell the model beforehand what kind of email can be spam or not spam. In order to do that we need to collect the data from users and ask them to filter few emails as spam or not spam.


### 1. Fetching the data
Download examples of spam and ham from Apache SpamAssassin’s public datasets: https://spamassassin.apache.org/old/publiccorpus/ • Unzip the datasets and familiarize yourself with the data format.
Here with the help of the link provided we downloaded the dataset for clasification as Spam or Ham as mentioned in the problem statement

### 2. Loading few emails
Over here the emails collected from the site will be used by us to rectify how many spam as well as ham mails are present in the data

Now that we have data with tagged emails — Spam or Not Spam, what should we do next? We would need to train the machine to make it smart enough to categorize the emails on its own. But, the machine can’t read the full statement and start categorizing the emails. Here we will need to use our NLP basics (check out my last blog).

### 3. Using python's email module to parse these emails
We will use python's email module to parse the given mails & thenhelps to identify the headers present in tht given data, encoding and so on. As parse helps to identify the headers, encoding , etc

### 4. Look at one example of ham and one example of spam, to get a feel of what the data looks like
After the parsing of emails present we will look on for the example of each spam as well as ham email. After observing the example of each emails we observe that the ham emails are more often plain texts whereas spam emails includes alot of html in it.Moreover, quite a few ham emails are signed using PGP, while no spam is. In 
short, it seems that the email structure is useful information to have.
This suggests that Spam & Ham have different structure of information.

### 5. Some emails are actually multipart, with images and attachments
Some emails consists alot of images & attachments(which consists of their own attachments).This helps to view the various structures in the emails such as plain , html, pgp etc.

### 6. Taking a look at the email headers
There's alot of information present in the emails which say alot more about the structure of the particular eamails & what this are present in that mails. but we are interested only in the "Subject" of the email present. So we will just have a look on the Subject of the email.

### 7. Split it into a training set and a test set
Here the data is splitted into training & testing set. In the training set the model is trained with the given data. With the help of testing set it is used to make predicted the predictions made by the model .

### 8. Learning too much about the data
Over here more detailed information odf the email is gathered.
1. We will need a function which helps us  to convert HTML to plain text .
2. The best way to do this would be to use the great BeautifulSoup library, but I would like to avoid adding another dependency to this project, so let's hack a quick & dirty solution using regular expressions.
3. The function first drops the <head> section, then converts all <a> tags to the word HYPERLINK, then it gets rid of all HTML tags, leaving only the plain text.
4.For readability, it also replaces multiple newlines with single newlines, and finally it unescapes html entities (such as &gt; or &nbsp;)
  eg- def html_to_plain_text(html).
  
 ### 9. Writing a function that takes an email as input and returns its content as plain text
  We will take email as an input in it & will return plaiin text as an out for the email. We will defie a function for that purpose
  eg- email_to_text(email)
  
### 10. Let's do more text preprocessing, technically-> stemming
  
  
