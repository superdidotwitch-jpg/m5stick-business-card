# M5StickS3 Business Card

A pocket digital business card running on an M5Stack M5StickS3. Switch it on and it loops an Instagram QR code and a flying-kick animation. Buttons and a shake bring up QR codes for Telegram, LinkedIn and a website, so people can scan whichever one they want.

All links and names in the code are placeholders. Put your own in before uploading (see "Make it yours" below).

## What it does

**When switched on**
- Shows the Instagram QR code, then the kick figure slides across the screen, over and over
- Battery level sits small in the corner
- 30 seconds with nothing pressed and it switches itself off

**While it is on**

| Action | Shows |
|---|---|
| Big front button (short press) | Telegram QR code |
| Small side button (short press) | LinkedIn QR code |
| Shake the stick | Website QR code |
| Hold either button about half a second | Back to the loop |
| Shake again while the website QR is showing | Back to the loop |

- A QR code stays on screen for one minute, then the stick switches itself off
- While a QR code is showing, another button or a shake jumps straight to that QR code
- Every button press makes a short click

## Hardware

- M5Stack M5StickS3 (built-in screen, two buttons, motion sensor, speaker and battery)
- A USB-C cable

Nothing else. No wiring, no soldering.

## Software

- Arduino IDE 2
- M5Stack board package (add the M5Stack boards URL in Preferences, then install "M5Stack" in Boards Manager)
- M5Unified library (Library Manager)
- Board setting: **M5StickS3**

## Make it yours

Open `firmware/business_card/business_card.ino`. Everything you need to change is at the top, under `Things you can change`:

| Setting | What to put |
|---|---|
| `igLink`, `igSmall` | Your Instagram link and the handle shown under the label |
| `tgLink`, `tgSmall` | Your Telegram link and handle |
| `liLink`, `liSmall` | Your LinkedIn link and the name shown under the label |
| `webLink`, `webSmall` | Your website link and the short address shown |

The same section also holds the timings, the shake strength, the click volume and the screen rotation, each with a comment saying what it does.

The kick figure is a 142 x 104 picture stored in the code as a list of colours (`kickPic`). Swap it for your own picture of the same size if you want a different figure.

## Uploading (the download mode trick)

On this stick the upload often fails with "port not found" because the stick is not listening for new code. Fix:

1. Plug the stick into the computer
2. Hold the side power button until the green light blinks
3. In Arduino IDE, pick the port that appears, then press Upload

## Repo layout

```
firmware/business_card/business_card.ino   the sketch
photos/                                    pictures of the card
```

## History

The stick started out as a planned mood pin (phrases and emojis on a button). It became this card instead: first a simple name, kick and one QR code sequence, then the loop with three QR codes, auto switch-off and the long press to go back, and finally the Instagram QR code on the loop screen.
