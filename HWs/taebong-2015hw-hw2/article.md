
##Looking Deep into Election Polls

<img width=600 height=300 src="http://i.huffpost.com/gen/613496/images/o-BOEHNER-MCCONNELL-facebook.jpg"/>

Election polling has been used for a long time to predict the results of elections. But how much can we trust it? Is election poll data really useful? Not really, without deep analysis. Many people even say, including pollsters, that election polling is in near crisis. The reason is that polling data has become very noisy due to the lack of response, and also varies from region to region due to different demographic compositions. So is election polling useless? 

The answer is NO. Data scientists are making in-depth and comprehensive analysis on polling data to make it valuable, not only in the prediction of the election results, but also in that this analysis unveils the factors that affect the result of elections and even shows how the factors evolved over time! These factors include the incumbency of candidates and the party that won in the previous term. As an example, here I show you my big-data analysis on the polling data regarding United States Senate election on 2014. 

In this analysis, I combined 777 polling data collected for US Senate election for 35 seats in 33 states, held on November 4, 2015. The collection dates of the polling data range from 23 months to 2 days before the election. Intuitively, the older polling data is less accurate than the newer. Moreover, some polls involve less number of participants than the others, and therefore contains more error, so-called sampling error. Thus, when combined, the polling data were assigned different weights; the newer polls and the polls with more participants are regarded more important than the older polls and the polls with less participants.

Another complication that rises when we analyze polling data is caused by the differences among the states in demographics, political leaning, incumbency, fund-rasings, race, and etc. Those differences result in the state-dependent bias in polling data. Therefore, I corrected for the bias by building some "state fundamentals" from US House data from 1896 to 1990.

Based on the polling data carefully combined and corrected, I performed the 10000 simulations of the number of Senate seats won by Republican party. The simulation result is shown in the Figure 1, along with the actual election result.


<figure>
    <a href="spread_hist.png">
       <img src="spread_hist.png" alt="Caption to image">
    </a>
<figcaption>
    <br><b>Figure 1.</b> The distribution of the simulated number of seats won by Republican party (blue) and the actual election result (red line). 
</figcaption>
</figure>
<br><br>
As shown in the figure, the simulated result is in fairly good agreement with the actual results. The most frequently simulation reports 22 seats, which differs by only one seat compared to the actual result! The width of the distribution of the simulated results reflects the accuracy of the estimation; the simulation predicts that with 95%, the number of Repulican seats is between 18 and 25. Pretty amazing, isn't it? 

Let's now see how well the bias-corrected combined polling data agrees with the actual results in each state. As shown in Figure 2, except for very few states, every actual result falls into the 95% confidence interval of the prediction.

<figure>
    <a href="spread_vs_state.png">
       <img src="spread_vs_state.png" alt="Caption to image">
    </a>
<figcaption>
    <br><b>Figure 2. </b> The difference between republican percentage and democrat percentage in each state. Green dot and shaded region represent the mean value and 95% confidence interval computed by using the bias-corrected, combined polling data, respectively. Red (repulican win) and blue (democrat win) dots represent the actual result.
</figcaption>
</figure>
<br><br>
As mentioned earlier, deep analysis of polling data not only predicts election result, but also reveals the evolution of the factors that affect elections. Figure 3 is the example of such analysis on the US House data from 1896 to 1990. The first three plots in the figure show the evolution of the effect of the following factors on the election, obtained by ordinary linear regression: the incumbency of candidate, the election result in the last previous election, and the party that won the last election. The last plot in the figure shows the reliablity of the analysis for each year. As shown in those plots, there was dramatic change in 1960. Before 1960, the effect of incumbency and party was minimal, but after 1960, they become significantly large; the incumbent candidates is more likely to be elected, and the party that won the last election is more likely to win the current election. I will leave the question of what happend in 1960 to you and political scientists. 

<figure>
    <a href="effect_vs_time.png">
       <img src="effect_vs_time.png" alt="Caption to image">
    </a>
<figcaption>
    <br><b>Figure 3.</b> The effect of incumbency, previous election result, the party that won the last election, and the $R^2$ value of linear regression as a function of time. 
</figcaption>
</figure>
<br><br>
Here I introduced the big data analysis of election polls, which transformed noisy and biased polling data into an accurate and precise prediction about the election, and unveiled the history of the factors - incombency, previous election result, and the party - that has been having influences on the previous polls. But what I have done here is a relatively simple analysis, and really a tip of iceberg. With more sophisticated analysis equipped with machine learning and other statistical techniques, we will even be able to connect poll data to political events, economical situations, election promises, and many other interesting factors. Politicians may utilize such analysis to simulate the result of election and build a effective campaign strategy. People may consult such analysis to predict the change in politics in advance, and prepare for the change. I will ask and answer the previous question again. Is election poll really useful? Absolutely, only with Big Data analysis. 


    
