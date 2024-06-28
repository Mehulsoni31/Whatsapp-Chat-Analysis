# Whatsapp-Chat-Analysis
Whatsapp Chat Analysis using NLP
Whatsapp has quickly become the world’s most popular text and voice messaging application. Specializing in cross-platform messaging with over 1.5 billion monthly active users, this makes it the most popular mobile messenger app worldwide.

I thought of various projects on which I could analyse data like - Air Quality Index or The cliched Covid-19 Data Analysis.

These would be some interesting insights for sure, more for me than for you, since the people in this chat are people I know personally.

# A streamlit app to analyze your whatsapp chats

Demo Link: (https://www.heroku.com/home)

# Exploratory Data Analysis

## Importing Necessary Libraries

I have used:

**Regex (re)** to extract and manipulate strings based on specific patterns.

References:

 [Regex - Python Docs](https://docs.python.org/3/library/re.html)
 
 [Regex cheatsheet](https://www.rexegg.com/regex-quickstart.html)
 
 [Regex Test - live](https://regexr.com/)
 
 [Datetime Format](http://strftime.org/)

1.pandas for analysis.

2.matlotlib and seaborn for visualization.

3. emoji to deal with emojis.

**References:**
 [Python Docs](https://pypi.org/project/emoji/)
 
 [Emoji](https://github.com/carpedm20/emoji)
 
 [EMOJI CHEAT SHEET](https://www.webfx.com/tools/emoji-cheat-sheet/)
 

4. wordcloud for the most used words.
   
6. datetime for datetime manipulation.


## Preparation and reading data

While reading each line, I split it based on a comma and take the first item returned from the split() function. If the line is a new message, the first item would be a valid date, and it will be appended as a new message to the list of messages. If it’s not, the message is part of the previous message, and hence, will be appended to the end of the previous message as one continuous message.

##  Pre-Processing

Firstly, let’s load our .txt into a DataFrame.

```
df = pd.DataFrame({'user_message': messages, 'message_date': dates})
    # convert message_date type
    df['message_date'] = pd.to_datetime(df['message_date'], format='%d/%m/%Y, %H:%M - ')

    df.rename(columns={'message_date': 'date'}, inplace=True)
```

##   The overall frequency of total messages on the group

![Line Graph presents here](https://github.com/Mehulsoni31/Whatsapp-Chat-Analysis/assets/71382200/804ad4bb-f207-4f18-ba53-90f3face6286)

##  Top 10 Most Active Days
![Top 10 Most Active Days](https://github.com/tusharnankani/whatsapp-chat-data-analysis/blob/main/assets/plots/top10_days.png)


##   Visualization

Now, we will be plotting grouped by day and respective group by month simultaneously, to see some interesting results.

![Visualization](https://github.com/tusharnankani/whatsapp-chat-data-analysis/blob/main/assets/plots/days_and_month.png)

## Inferences

1. The group is most active on Sundays, and least active on Mondays (probably Monday Blues.)


2. Also, Saturday has a minor drop, this is probably due to the fact that Saturday is the first weekend after Friday and people are usually taking a rest and doing other activities than messaging on their phones.


3. The group has been recently very active, in September.

   To get a clearer understanding, we will plot a combined graph — Heatmap.

##   Heatmap of Month sent and Day sent

![Heatmap](https://github.com/tusharnankani/whatsapp-chat-data-analysis/blob/main/assets/plots/month_day_heatmap.png)

##   Most Used Words in the chat

![WordCloud](https://github.com/tusharnankani/whatsapp-chat-data-analysis/blob/main/assets/plots/wordcloud.png)



