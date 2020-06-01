# How does Super Bowl affect TV viewership and musician rating?

Whether or not you like football, the Super Bowl is a spectacle. There's drama in the form of blowouts, comebacks, and controversy in the games themselves. There are the ridiculously expensive ads, some hilarious, others gut-wrenching, thought-provoking, and weird. The half-time shows with the biggest musicians in the world, sometimes [riding giant mechanical tigers](https://youtu.be/ZD1QrIe--_Y?t=1) or [leaping from the roof of the stadium](https://youtu.be/mjrdywp5nyE?t=62).

![super-bowl-liv-spectacle-mahomes-jlo-shakira](https://user-images.githubusercontent.com/65482013/83346749-dd09e580-a33c-11ea-8fc0-54df39207d91.jpg)

In this project, we will find out how some of the elements of this show interact with each other. We will answer questions like:

<li> What are the most extreme game outcomes?
<li> How does the game affect television viewership?
<li> How have viewership, TV ratings, and ad cost evolved over time?
<li> Who are the most prolific musicians in terms of halftime show performances?

## The Data
The dataset we'll use was scraped and polished from Wikipedia. It is made up of three CSV files, one with [game data](https://en.wikipedia.org/wiki/List_of_Super_Bowl_champions), one with [TV data](https://en.wikipedia.org/wiki/Super_Bowl_television_ratings), and one with [halftime musician data](https://en.wikipedia.org/wiki/List_of_Super_Bowl_halftime_shows) for all 52 Super Bowls through 2018.

## Preprocessing the Data

For the Super Bowl game data, we can see the dataset appears whole except for missing values in the backup quarterback columns, which make sense given most starting QBs in the Super Bowl play the entire game. The Super Bowl goes all the way back to 1967, and the more granular columns (e.g. the number of songs for halftime musicians) probably weren't tracked reliably over time. Wikipedia is great but not perfect.

For the TV data, the following columns have missing values and a lot of them:
<ul>
<li><code>total_us_viewers</code> (amount of U.S. viewers who watched at least some part of the broadcast)</li>
<li><code>rating_18_49</code> (average % of U.S. adults 18-49 who live in a household with a TV that were watching for the entire broadcast)</li>
<li><code>share_18_49</code> (average % of U.S. adults 18-49 who live in a household with a TV <em>in use</em> that were watching for the entire broadcast)</li>
</ul>
For the halftime musician data, there are missing numbers of songs performed (<code>num_songs</code>) for about a third of the performances.

Though it would be nice to have this data, the effort to fetch this data and incorporate into the dataset is too much and the insights obtained do not seen worth it, since most of the missing data is historical data of the 90s.

## Point difference distribution

Most combined scores are around 40-50 points, with the extremes being roughly equal distance away in opposite directions. Going up to the highest combined scores at 74 and 75, we find two games featuring dominant quarterback performances. One even happened recently in 2018's Super Bowl LII where Tom Brady's Patriots lost to Nick Foles' underdog Eagles 41-33 for a combined score of 74.

Going down to the lowest combined scores, we have Super Bowl III and VII, which featured tough defenses that dominated. We also have Super Bowl IX in New Orleans in 1975, whose 16-6 score can be attributed to inclement weather. The field was slick from overnight rain, and it was cold at 46 °F (8 °C), making it hard for the Steelers and Vikings to do much offensively. This was the second-coldest Super Bowl ever and the last to be played in inclement weather for over 30 years. The NFL realized people like points, I guess!

## Do blowouts translate to lost viewers?

The vast majority of Super Bowls are close games. Makes sense. Both teams are likely to be deserving if they've made it this far. The closest game ever was when the Buffalo Bills lost to the New York Giants by 1 point in 1991, which was  best remembered for Scott Norwood's last-second missed field goal attempt that went [wide right](https://www.youtube.com/watch?v=RPFZCGgjDSg), kicking off four Bills Super Bowl losses in a row. Poor Scott. The biggest point discrepancy ever was 45 points! where Hall of Famer Joe Montana's led the San Francisco 49ers to victory in 1990, one year before the closest game ever.

I remember watching the Seahawks crush the Broncos by 35 points (43-8) in 2014, which was a boring experience in my opinion. The game was never really close. I'm pretty sure we changed the channel at the end of the third quarter. Let's combine our game data and TV to see if this is a universal phenomenon and to answer the question **Do large point differences translate to lost viewers?** We can plot [household share](https://en.wikipedia.org/wiki/Nielsen_ratings)(average percentage of U.S. households with a TV in use that were watching for the entire broadcast) vs. point difference to find out.

## The costly halftime shows. Are they worth it?

Plotitng a time-graph, we see that the viewers increased before ad costs did. Maybe the networks weren't very data savvy and were slow to react?

It turns out Michael Jackson's Super Bowl XXVII performance, one of the most watched events in American TV history, was when the NFL realized the value of Super Bowl airtime and decided they needed to sign big name acts from then on out. The halftime shows before MJ indeed weren't that impressive, which we can see by filtering our [halftime_musician data](https://en.wikipedia.org/wiki/List_of_Super_Bowl_halftime_shows).

## Who performed the most songs in a halftime show?

The world famous [Grambling State University Tiger Marching Band](https://www.youtube.com/watch?v=RL_3oqpHiDg) takes the crown with six appearances. Beyoncé, Justin Timberlake, Nelly, and Bruno Mars are the only post-Y2K musicians with multiple appearances (two each).

## 10. Conclusion

So most non-band musicians do 1-3 songs per halftime show. It's important to note that the duration of the halftime show is fixed (roughly 12 minutes) so songs per performance is more a measure of how many hit songs you have. JT went off in 2018, wow. 11 songs! Diana Ross comes in second with 10 in her medley in 1996.

In this project, we loaded, cleaned, then explored Super Bowl game, television, and halftime show data. We visualized the distributions of combined points, point differences, and halftime show performances using histograms. We used line plots to see how ad cost increases lagged behind viewership increases. And we discovered that blowouts do appear to lead to a drop in viewers!
