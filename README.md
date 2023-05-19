# Predicting Authoritarian Sentiment #

## Problem Statement ##

The rise of Authoritarianism is a growing concern among democratic societies worldwide. To gain and maintain power, Authoritarian leaders require a base of followers who support their ideology and policies. In this project, I aim to predict support for Authoritarianism using data from the World Values Survey dataset. This dataset includes responses from individuals in various countries regarding their attitudes towards governance, society, and culture. By analyzing the WVS dataset using machine learning models, I seek to identify factors that contribute to support for Authoritarianism, such as economic insecurity, cultural conservatism, and distrust of institutions. The results of this project could provide insights into the underlying causes of Authoritarianism and inform strategies to prevent its spread in democratic societies.

## Data Dictionaries

### Component Variables of **Authoritarianism Index**

| Question ID | Question Description | Response Scale | Directionality |
|---|---|---|---|
| A042 | "Here is a list of qualities that children can be encouraged to learn at home. Which, if any, do you consider to be especially important? Please choose up to five" (**Obedience**) | 0 (not mentioned) to 1 (important) | Positive |
| E018 | "I'm going to read out a list of various changes in our way of life that might take place in the near future. Please tell me for each one, if it were to happen, whether you think it would be a good thing, a bad thing, or don't you mind?" (**Greater respect for authority**) | 1 (good thing) to 3 (bad thing) | Negative |
| E114 | "I'm going to describe various types of political systems and ask what you think about each as a way of governing this country. For each one, would you say it is a very good, fairly good, fairly bad or very bad way of governing this country?" (**Having a strong leader**) | 1 (very good) to 4 (very bad) | Negative |
| E116 | "I'm going to describe various types of political systems and ask what you think about each as a way of governing this country. For each one, would you say it is a very good, fairly good, fairly bad or very bad way of governing this country?" (**Having the army rule**) | 1 (very good) to 4 (very bad) | Negative |

### Other Questions for Use in Modelling

| Question ID | Question Description | Response Scale | Directionality |
|---|---|---|---|
| A004, A005, A006 | "For each of the following aspects, indicate how important it is in your life" (**Politics, Work, Religion**) | 1 (very important) to 4 (Not at all important) | Negative |
| A008 | "Taking all things together, would you say you are:" (**Happiness**) | 1 (very happy) to 4 (not at all happy) | Negative |
| A029, A030, A032, A034, A035, A039, A040, A041 | "Here is a list of qualities that children can be encouraged to learn at home. Which, if any, do you consider to be especially important? Please choose up to five" (**Independence, Hard work, Feeling of responsibility, imagination, tolerance and respect for other people, determination/perseverance, religious faith, unselfishness**) | 0 (not mentioned) to 1 (important) | Positive |
| A124_02, 03, 06, 07, 08, 09 | "On this list are various groups of people. Could you please mention any that you would not like to have as neighbors?" (**People of a different race, Heavy drinkers, Immigrants/foreign workers, People who have AIDS, Drug addicts, Homosexuals**) | 0 (not mentioned) to 1 (mentioned) | Positive |
| A165 | "Generally speaking, would you say that most people can be trusted or that you need to be very careful in dealing with people?" | 1 (Most people can be trusted) to 2 (Need to be very careful) | Negative |
| A170 | "All things considered, how satisfied are you with your life as a whole these days?" | 1 (Dissatisfied) to 10 (Satisfied) | Positive |
| D054 | "One of my main goals in life has been to make my parents proud" | 1 (Strongly agree) to 4 (Strongly disagree) | Negative |
| D059 | "Men make better political leaders than women do" | 1 (Strongly agree) to 4 (Strongly disagree) | Negative |
| D060 | "University is more important for a boy than for a girl" | 1 (Strongly agree) to 4 (Strongly disagree) | Negative |
| E003 | "If you had to choose, which one of the things on this card would you say is most important?" | **Categorical**: 1 = 'Maintaining order in the nation', 2 = 'Giving people more say in important government decisions', 3 = 'Fighting rising prices', 4 = 'Protecting freedom of speech' | Not Applicable |
| E015, E016 | "I'm going to read out a list of various changes in our way of life that might take place in the near future. Please tell me for each one, if it were to happen, whether you think it would be a good thing, a bad thing, or don't you mind?" (**Less importance placed on work, More emphasis on technology**) | 1 (good thing) to 3 (bad thing) | Negative |
| E023 | "How interested would you say you are in politics?" | 1 (Very interested) to 4 (Not at all interested) | Negative |
| E069_01, 02, 04, 05, 06, 10, 11, 12, 13, 14, 15 | "I am going to name a number of organizations. For each one, could you tell me how much confidence you have in them" (**Churches, Armed Forces, Labour Unions, Police, Television, The Government, Political Parties, Major Companies, Environmental Protection Movement, Women's Movement**) | 1 (A great deal) to 4 (None at all) | Negative |
| F028 | "Apart from weddings, funerals and christenings, about how often do you attend religious services these days?" | 1 (More than once a week) to 8 (Never, practically never) | Negative |
| F063 | "How important is God in your life?" | 1 (Not at all important) to 10 (Very important) | Positive |
| F116, F117, F118, F120, F121, F123 | "Please tell me for each of the following actions whether you think it can always be justified, never be justified, or something in between" (**Cheating on taxes, Someone accepting a bribe, Homosexuality, Abortion, Divorce, Suicide**) | 1 (Never justifiable) to 10 (Always justifiable) | Positive |

### Demographic Variables

| Variable ID | Variable Description | Response Scale | Directionality | Model |
|---|---|---|---|---|
| X001 | sex | **Categorical**: 1 = male, 2 = female | NA | Regression |
| X003 | Age (at time of interview) | **Numeric** | NA | Regression |
| X007 | Marital status | **Categorical**: 1 = 'Married', 2 = 'Living together', 3 = 'Divorced', 4 = 'Separated', 5 = 'Widowed', 6 = 'Single' | NA | Regression |
| X011 | Number of children | **Numeric** | NA | Regression |
| X025R | Education level (Recoded into three groups) | 1 (Lower) to 3 (Higher) | Positive | Regression |
| X028 | Employment status | **Categorical**: 1 = 'Full time (> 30hr/wk)', 2 = 'Part time (< 30hr/wk)', 3 = 'Self employed', 4 = 'Retired/pensioned', 5 = 'Housewife not otherwise employed', 6 = 'Student', 7 = 'Unemployed', 8 = 'Other' | NA | Regression |
| X045 | Social class (subjective/self described) | 1 (Upper class) to 5 (Lower class) | Negative | Regression |
| X047R_WVS | Income level (subjective, recoded into three groups) | 1 (low) to 3 (high) | Positive | Regression |
| COUNTRY_ALPHA | Country of Respondent | Categorical: Three-Letter Country Code | NA | Time-Series |
| S002VS | Survey Wave | Numeric | NA | Time-Series |
| S020 | Year of Interview | Numeric/Datetime | NA | Time-Series |

***Note**: Response scales are **ordinal** unless otherwise specified*

*Scales determined with reference to https://www.worldvaluessurvey.org/WVSOnline.jsp*

## Conclusions

This project aimed to predict support for authoritarianism using data from the World Values Survey dataset. The findings reveal that authoritarian thinking is related to attitudes towards religion, divorce, abortion, homosexuality, and misogyny, and is particularly prevalent in Latin America and the Middle East. The machine learning model proved relatively effective at predicting support for authoritarianism, achieving 71% accuracy over a 63% baseline. These results provide valuable insights into the underlying causes of authoritarian sentiment and can inform strategies to prevent its spread in democratic societies.

## Next Steps

- Delve further into the relationship between economic insecurity and support for authoritarianism
- Investigate the role of social media in the spread of authoritarianism
- Compare individual attitudes towards authoritarianism to measures of societal oppression such as the Human Freedom Index