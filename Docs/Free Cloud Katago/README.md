# Two Free Ways to Run Cloud KataGo

```Last updated: 1 Nov 2026, Katago v1.18.2```

These two options can be used **individually or together**, depending on how much cloud GPU time you need.

The latest version tested on [SWHub](https://github.com/SoumyaK4/SWHub), but should work fine in Katrain or similar apps that supports JSON based Cloud KataGo.

## 1. Google Colab

Google Colab provides access to a **T4 GPU**, usually giving around **3–5 hours of free GPU usage per day**, depending on availability.

### Pros

* More free GPU usage overall.
* No card is required.

### Cons

* Colab may disconnect the runtime if the notebook itself receives no interaction for roughly **10 minutes**.
* Because of this, you need to run the full setup again whenever you start a fresh session. This usually takes around roughly **5 minutes**.

---

## 2. Modal

Modal provides **$30 of free credits every month**.

### Pros

* After the initial setup, you generally don't need to manage the server manually.
* The server automatically shuts down when it is not being used, so credits aren't wasted.
* Storage remains **persistent**, so you don't need to download and set everything up again each time.
* You can set your usage limit to **$29** in Modal's settings so your card won't be charged if you reach the free-credit limit.
* The free credits reset at the beginning of every month.

### Con

* To receive the **$30/month free credits**, you need to link a card during the initial setup.
* Modal may make a small **one-time verification charge of around $0.50** to confirm the card.

---

## Recommended Setup

If you can link a card once to unlock Modal's free monthly credits, I recommend using:

**Modal as your main server → Google Colab as your backup**

Use Modal normally throughout the month. Once you use up the monthly free credits, switch to Google Colab until Modal's credits reset the following month.

This gives you the convenience of Modal's **persistent storage and automatic server shutdown** while still letting you use Colab for additional free GPU time when needed.

Most importantly, you won't have to repeat the full KataGo setup every time you want to use Cloud KataGo. You only need to deal with Colab's setup process after exhausting your Modal credits.

---

# Setup

| What you want to do | Google Colab | Modal |
| --- | --- | --- |
| **Play and analyse** | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SoumyaK4/SWHub/blob/SWHub/Docs/Free%20Cloud%20Katago/Analysis/Kata_Colab.ipynb) | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SoumyaK4/SWHub/blob/SWHub/Docs/Free%20Cloud%20Katago/Analysis/Kata_Modal.ipynb) |
| **Contribute to KataGo training** | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SoumyaK4/SWHub/blob/SWHub/Docs/Free%20Cloud%20Katago/Contribute/Kata_Colab_Contribution.ipynb) | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SoumyaK4/SWHub/blob/SWHub/Docs/Free%20Cloud%20Katago/Contribute/Kata_Modal_Contribution.ipynb) | 

# Issues

If you run into any issues, then you can contact me -> 


<a href="https://discord.gg/ptjzTWU9SP"><img alt="Discord chat: members online" src="https://img.shields.io/discord/1369452545730285698?label=SWHub&amp;logo=discord&amp;logoColor=white&amp;color=35664a"></a> 

**[Computer Go Community](https://discord.gg/5aTGusWxvc)**
