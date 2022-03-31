# PHISHING 101
This project is a collaboration between myself, [Joe Kramer](https://github.com/Githubjoe999), and [Josh Sitompul](GitHub.com/korvuswraith).

# Demonstration of a phishing attack 

In this project, we demonstrate how a phishing attack works. We then use the demonstration to deliver a lesson on avoiding phishing attacks in the future. 

*Everything in this demo is for educational purposes only.  These techniques can cause serious harm - do not use them in an illegal or malicious way.*

## Educational Deck

You can view the educational module [here](https://docs.google.com/presentation/d/1tHViKoNmyG9BW4bdVqVQzv6lz4ILUpxxzoyB1XbFikY/edit?usp=sharing) (made on Google Slides).

## Video Presentation

(space reserved for link to video)

## Background

For the final project in our bootcamp, were assigned to create a 5-10 minute video demonstrating something related to the field of cybersecurity - an incredibly broad set of instructions, that was actually really exciting for us - there were a ton of possibilities. 

We discussed a few different ideas for this project, and we all immediately liked the idea of demonstrating a phishing attack. It involved a few different technical skills we wanted to explore more, so it would be a useful opportunity for us to learn something new. Also, it's a topic that's constanly in the news, so it's a relevant topic. 

As we explored the topic a bit more, there were a few technical questions we knew we needed to figure out, like how we would perform the exploit and how to send the email without getting flagged as malicious, but overall it felt very doable.  

We were set. 

## The Exploit

We ultimately decided to demonstrate 2 different types of phishing attacks - credential harvesting and system compromise.

### Credential Harvesting

We created a Twitter account ([@ceovulnerable](https://twitter.com/ceovulnerable)) that would be the target of our phishing attack. We also created two email accounts (using Protonmail), one for our attacker and one for our target.

For the actual stealing of the credentials, we used a program called [Zphisher](https://github.com/htr-tech/zphisher), although there are several similar tools fulfilling a similar function. We went with Zphisher because it automates several steps in the attack process - it has pre-made website templates spoofing many different popular sites, it has different options for hosting the malicious site, and it operates the listener to receive the credentials. 

The last bit was reverse engineering a realistic Twitter email, which was a little trickier than expected. In the end, we manually created an email, structuring it to look as close as possible to a real login notification email from Twitter. 

As you can see in the video, the phishing attack was really straightforward to pull off with these tools. 

### System Compromise

The next step was doing a more active exploitation - getting a reverse shell on a victim's computer by getting them to download & run a malicious file. There were a couple of new technical problems to solve for this exercise. We needed to create the payload and a way for it to reach our computer. In all the practice we had done, we could get a payload to reach out from within the same network, but for this one, we needed the payload to be able to reach out over the internet to a remote server. 

For this, we used a service called [ngrok](https://ngrok.com/), which basically gives you a URL that tunnels to your computer.  From there, you set up a listener targeting whatever port ngrok is set up on, and you can receive connections from the URL.   

We made the payload using msfvenom that was set to reach out to the URL from ngrok and create a meterpreter reverse shell. The only thing left at that point was to set up a listener on metasploit, and the demo was ready to go.

## Learning Module

Once we had the technical parts of the project finished, the educational content wwas the last part to figure out.  We knew we wanted to use this as an opportunity to teach viewers about phishing attacks - what they are, how they work, and most importantly, how to avoid getting caught in one.  This part was more straightforward, but it boiled down to getting some good stats on phishing attacks in the wild, and coming up with some useful tips on how to identify suspicious emails. 

This part of the project also hopefully showcases our communication skils, as well as our ability to create and deliver training materials. 

## Conclusion

We hope this video is useful for any viewers who have received phishing emails before (so, everyone).  Be careful with your emails, people, and stay safe out there! 
