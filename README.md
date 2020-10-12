# Foodie_chat_bot

## Problem Statement
The main purpose of the bot is to help users discover restaurants quickly and efficiently and to provide a good restaurant discovery experience. An Indian startup named 'Foodie' wants to build a conversational bot (chatbot) which can help users discover restaurants across several Indian cities.

**The bot takes the following inputs from the user:**
*City: Take the input from the customer as a text field. For example:*

        Bot: In which city are you looking for restaurants?
        User: anywhere in Delhi
        
        
**Foodie works only in Tier-1 and Tier-2 cities** :
 - **Tier 1 cities :** Ahmedabad, Bengaluru, Chennai, Delhi, Hyderabad, Kolkata, Mumbai, and Trichy, Jaipur, Coimbatore
 - **Tier 2 cities :** 	Agra, Ajmer, Aligarh, Amravati, Amritsar, Asansol, Aurangabad, Bareilly, Belgaum, Bhavnagar, Bhiwandi, Bhopal, Bhubaneswar, Bikaner, Bilaspur, Bokaro Steel City, Chandigarh, Coimbatore, Cuttack, Dehradun, Dhanbad, Bhilai, Durgapur, Dindigul, Erode, Faridabad, Firozabad, Ghaziabad, Gorakhpur, Gulbarga, Guntur, Gwalior, Gurgaon, Guwahati, Hamirpur, Hubli–Dharwad, Indore, Jabalpur, Jaipur, Jalandhar, Jammu, Jamnagar, Jamshedpur, Jhansi, Jodhpur, Kakinada, Kannur, Kanpur, Karnal, Kochi, Kolhapur, Kollam, Kozhikode, Kurnool, Ludhiana, Lucknow, Madurai, Malappuram, Mathura, Mangalore, Meerut, Moradabad, Mysore, Nagpur, Nanded, Nashik, Nellore, Noida, Patna, Pondicherry, Purulia, Prayagraj, Raipur, Rajkot, Rajahmundry, Ranchi, Rourkela, Salem, Sangli, Shimla, Siliguri, Solapur, Srinagar, Surat, Thanjavur, Thiruvananthapuram, Thrissur, Tiruchirappalli, Tirunelveli, Ujjain, Bijapur, Vadodara, Varanasi, Vasai-Virar City, Vijayawada, Visakhapatnam, Vellore and Warangal
 - The bot is able to identify common synonyms of city names, such as Bangalore/Bengaluru, Mumbai/Bombay etc.
 - The Chatbot made in a way that should provide results for tier-1 and tier-2 cities only, while for tier-3 cities, it replies back with something like "We do not operate in that area yet".
 
 - **Cuisine Preference :** Take the cuisine preference from the customer. The bot should list out the following six cuisine categories (Chinese, Mexican, Italian, American, South Indian & North Indian) and the customer can select any one out of that. Following is an example for the same:

    For Example :
        Bot: What kind of cuisine would you prefer?

        Chinese
        Mexican
        Italian
        American
        South Indian
        North Indian
        User: I’ll prefer Italian!
        
 - Average budget for two people: It has Segment feature for the price range (average budget for two people) into three price categories: lesser than 300, 300 to 700 and more than 700. The bot will asks the user to select one of the three price categories. 
 
     For example:

        Bot: What price range are you looking at?

        Lesser than Rs. 300
        Rs. 300 to 700
        More than 700
        User: in range of 300 to 700
        
- While showing the results to the user, the bot displays the top 5 restaurants in a sorted order (descending) of the average Zomato user rating (on a scale of 1-5, 5 being the highest). The format is: {restaurant_name} in {restaurant_address} has been rated {rating}.

- Finally, the bot will ask the user whether he/she wants the details of the top 10 restaurants on email. If the user replies 'yes', the bot should ask for user’s email id and then send it over email. Else, just reply with a 'goodbye' message. The mail will having the following details for each restaurant:

        Restaurant Name
        Restaurant locality address
        Average budget for two people
        Zomato user rating
        
**This Project is buld on Rasa Framework. Rasa is a framework for developing AI powered, industrial grade chatbots. It's incredibly powerful, and is used by developers worldwide to create chatbots and contextual assistants. In this project, we are going to understand some of the most important basic aspects of the Rasa framework and chatbot development.
**


# Installation guide

Requirements:

1. Python (requires Python 3.6.0 or higher)
2. Creating a virtual environment, I strongly recommend that you create a virtual environment before installing Rasa and Rasa X. Virtual environment tools like virtualenv and virtualenvwrapper provide isolated Python environments. They help you install packages without any dependency conflicts and root privileges.
3. Installing Rasa and Rasa X:

      You can install both Rasa and Rasa X using the following code:

      $ pip install rasa-x --extra-index-url https://pypi.rasa.com/simple
      Use the following code only if you want to install Rasa:
      $ pip install rasa 

4. Install Rasa NLU and Spacy in the same command prompt:

      $ pip install rasa[spacy]

      $ python -m spacy download en_core_web_md

      $ python -m spacy link en_core_web_md en
      
5. After setting up everything
      Activate rasa env then follow the following commands to asses the bot
      **1.Train Test NLU Model**
      - train model : rasa train nlu
      - to test : rasa shell nlu
      
      **2.Train Test Core Model**
      
      - train core : rasa train core
      *To test core model rasa need action server only just because we're using custom zomato api function*
      - run action server *(on another terminal)*: rasa run action
      - test core : rasa shell (if its showing domain error i.e, pass this rasa train -vv -dump-stories --force)
     


# Thank you !
