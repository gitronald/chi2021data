 
# Characterizing Problematic Email Reply Suggestions

This repository contains the dataset for "I Can’t Reply with That": Characterizing Problematic Email Reply Suggestions, which is to be published in the _Proceedings of the 2021 ACM Conference on Human Factors in Computing Systems_. 

The dataset comes from section four of the paper - Issue Evaluation: Experiments - where we further assessed the potential impact of both content and contextual cues on the perceived appropriateness of suggested email replies through a series of online crowd experiments.

In our experiments, we asked judges to provide quantitative ratings and qualitative feedback on email-reply scenarios we derived from our interviews, online anecdotes, publicly available email corpora, and reply suggestions from a major email provider (see sections 4.2 and 4.3 in the paper for additional detail).

The set of email-reply scenarios that we designed consisted of (1) a social tie (i.e. who the email was from) and structural features (i.e. email greetings and closings) that we experimentally varied, and (2) an email-reply pair, consisting of the body of a hypothetical email and a hypothetical reply.

In total, we constructed 132 unique email-reply pairs, and collected 9,504 ratings (6 ratings for each email-reply pair under the experimental conditions) from 259 unique judges.
For each rating, participants completed several Likert scale responses and had the opportunity to submit a correction to the email reply to make it more appropriate, as well as to submit an explanation for that correction. 
In total, 96% of judges submitted at least one correction, and 70% of tasks contained a judge-generated correction (see section 4.5.4 for our analysis of these corrections).


### The Data

`final_public.tsv`  

Each row corresponds to a single email-reply scenario judgement, and has the following columns, which have been grouped for convenience:

#### Judgement IDs
`JudgeID` : An anonymous judge ID  
`pair_id` :  a unique ID for the email-reply pair  
`scenario_id` : a unique ID for the scenario (email-reply + social tie + structure)  

#### Judgement metadata
`category` : the category for the email-reply pair  
`social_tie` : the social tie the email is from  
`email_structure` : a boolean for whether the greeting/closing were included  
`counterbalance` : the counterbalancing group  
`hierarchy` : factor indicating whether relationship has low or high hierarchy  
`relationship` : factor indicating relationship type (professional, personal, family)  
`timer` : time in seconds spent on this judgement  
`timer_bins_meta` : binned time variable  

#### Judgement content 
`email_from` : who the email is from  
`email_greeting` : the greeting used at the top of the email  
`email_closing` : the closing used at the end of the email  
`email_body` : the body of the email being judged  
`email_context` : the first sentence of the email  
`email_act` : the second sentence of the email  
`email_reply` : the reply to the email  

#### Likert ratings
`appropriate` : Likert scale rating for how the appropriate the reply is  
`positive` : Likert scale rating for how the positive the reply is  
`polite` : Likert scale rating for how the polite the reply is  
`professional` : Likert scale rating for how the professional the reply is  
`sufficient` : Likert scale rating for how the sufficient the reply is  

#### Binary and free text responses
`would_send` : a binary response indicating if judge would send email as is  
`adjustment` : text response, how the judge would adjust to the email before sending it  
`adjustment_rationale` : text response, the judge's rationale for their adjustment  
`adjusted` : a boolean indicating if the judge changed the reply  

#### Word counts and classifications
`num_words_{email_body,email_reply,adjustment}` : number of words in each text column  
`num_char_{email_body,email_reply,adjustment}` : number of chars in each text column  
`short_email` : boolean classification of email  
`num_words_diff_adjustment` : number of words added or removed while adjusting the reply  
