# How-does-Super-Bowl-affect-TV-viewership-and-musician-rating?

Whether or not you like football, the Super Bowl is a spectacle. There's drama in the form of blowouts, comebacks, and controversy in the games themselves. There are the ridiculously expensive ads, some hilarious, others gut-wrenching, thought-provoking, and weird. The half-time shows with the biggest musicians in the world, sometimes [riding giant mechanical tigers](https://youtu.be/ZD1QrIe--_Y?t=1) or [leaping from the roof of the stadium](https://youtu.be/mjrdywp5nyE?t=62).

![super-bowl-liv-spectacle-mahomes-jlo-shakira](https://user-images.githubusercontent.com/65482013/83346749-dd09e580-a33c-11ea-8fc0-54df39207d91.jpg)

In this project, we will find out how some of the elements of this show interact with each other. We will answer questions like:
<ul>
<li>What are the most extreme game outcomes?
<li>How does the game affect television viewership?s<li>How have viewership, TV ratings, and ad cost evolved over time?
<li>Who are the most prolific musicians in terms of halftime show performances?
<\ul>

## The Data
The dataset we'll use was scraped and polished from Wikipedia. It is made up of three CSV files, one with [game data](https://en.wikipedia.org/wiki/List_of_Super_Bowl_champions), one with [TV data](https://en.wikipedia.org/wiki/Super_Bowl_television_ratings), and one with [halftime musician data](https://en.wikipedia.org/wiki/List_of_Super_Bowl_halftime_shows) for all 52 Super Bowls through 2018.

## Preprocessing the Data

For the Super Bowl game data, we can see the dataset appears whole except for missing values in the backup quarterback columns, which make sense given most starting QBs in the Super Bowl play the entire game. The Super Bowl goes all the way back to 1967, and the more granular columns (e.g. the number of songs for halftime musicians) probably weren't tracked reliably over time. Wikipedia is great but not perfect.

<p>For the TV data, the following columns have missing values and a lot of them:</p>
<ul>
<li><code>total_us_viewers</code> (amount of U.S. viewers who watched at least some part of the broadcast)</li>
<li><code>rating_18_49</code> (average % of U.S. adults 18-49 who live in a household with a TV that were watching for the entire broadcast)</li>
<li><code>share_18_49</code> (average % of U.S. adults 18-49 who live in a household with a TV <em>in use</em> that were watching for the entire broadcast)</li>
</ul>
<p>For the halftime musician data, there are missing numbers of songs performed (<code>num_songs</code>) for about a third of the performances.</p>
Though it would be nice to have this data, the effort to fetch this data and incorporate into the dataset is too much and the insights obtained do not seen worth it. Also most of the msissing data is historical data of the 90s.
