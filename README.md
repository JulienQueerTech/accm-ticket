# Simple slack bot for ACCM

Tested with python3

## Installing slackclient

    pip install slackclient --user

## Installing fastText

    cd ACCM-bot/accmbot
    git clone https://github.com/facebookresearch/fastText.git
    cd fastText/
    make

This is also [well documented online](https://fasttext.cc/docs/en/support.html) and there are even some [unofficial instructions for Windows](https://www.cs.mcgill.ca/~mxia3/FastText-for-Windows/).
If you install fastText somewhere else than in the `accmbot` folder, then you will need to adapt the `fasttext_cmd` variable in `fasttext.py`.

code was integrated in the Slack bot of JP (cc @JP Lapierre). I know he uploaded to *some* gitlab (their personal one), because we didn't have permissions set up to push code at SekhmetDesign/ACCM3. 

Instructions : for our part (which classifies incoming messages into "Spell out an answer", "Urgent", "We have a template answer to this sort of demand" and "Ignore") you need to install the "fasttext" python library (developed by facebook). It's well documented (e.g. https://fasttext.cc/docs/en/supervised-tutorial.html), one way is

$ wget https://github.com/facebookresearch/fastText/archive/v0.1.0.zip $ unzip v0.1.0.zip
$ cd fastText-0.1.0 $ make

Now you have the fasttext executable (probably in `./bin/fasttext`). Next you need the file of the trained model (2.6 Mb), which JP should push along with the code. 
Somewhere in the code, you have to set paths to those two things, the fasttext binary and the model file.

You can query the thing by saying "bot <message>" in certain Slack channels, and the bot will answer the message (this is more JP's to document I think). My plan was to develop that further into making draft suggestions for the volunteer to build upon (and readily write down the template answers, which we have, in those cases), but we were missing some corpus from Andreas (and time) to implement that.

I didn't see BaoPhac's doc so I'm not entirely sure how they did that, my plan was for the Slack bot to push incoming messages to FreshDesk =the ticketing system (so that we can do some NLP analysis and suggestions for the volunteer at the bot stage), but during the presentation he mentioned having used another integration service... I didn't get that part, can't help you much with it as it stands ^^ (ask BaoPhac & JP).

After the hackathon I did http://queer-search.glitch.me/ which might be useful for some other feature demands from ACCM, tell me if you want more about that. 
