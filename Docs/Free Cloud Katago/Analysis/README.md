# Two Free Ways to Run Cloud KataGo

```Last updated: 3 Oct 2026, Katago v1.18.2```

These two options can be used **individually or together**, depending on how much cloud GPU time you need.

The latest version tested on [SWHub](https://github.com/SoumyaK4/WeiqiHub), but should work fine in Katrain or similar apps that supports Cloud KataGo.

## 1. Google Colab

Google Colab provides access to a **T4 GPU**, usually giving around **3–5 hours of free GPU usage per day**, depending on availability.

### Pros

* More free GPU usage overall.
* No card is required.

### Cons

* Colab may disconnect the runtime if the notebook itself receives no interaction for roughly **10 minutes**.
* Storage is not persistent, so downloaded files are lost when the runtime is reset.
* Because of this, you need to run the full setup again whenever you start a fresh session. This usually takes around **7–10 minutes**.

---

## 2. Modal

Modal provides **$30 of free credits every month**.

### Pros

* After the initial setup, you generally don't need to manage the server manually.
* The server automatically shuts down when it is not being used, so credits aren't wasted on an idle instance.
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

# Download & Setup

Download the Google Colab or Modal Jupyter Notebook here:

**[Google Colab Jupyter Notebook](./Kata_Colab.ipynb)**

**[Modal Jupyter Notebook](./Kata_Modal.ipynb)**

Download the notebook for the service you want to use, then upload it to the respective platform.

The **platform-specific setup instructions are included inside each notebook**.
