\# 📈 Nifty Valuation Indicator

A lightweight, single-file web application that helps investors analyze whether the Nifty 50 index is currently **"Cheap" (Undervalued)** or **"Costly" (Overvalued)** based on historical growth trends.

[**View Live Demo**](https://a3986.github.io/nifty-valuation-tool/) 
## **📖 Table of Contents**

* [Features](#features)  
* [How It Works](#how-it-works)  
* [Tech Stack](#tech-stack)  
* [Installation & Usage](#installation--usage)  
* [Configuration](#configuration)  
* [Deployment](#deployment)  
* [Disclaimer](#disclaimer)

## **🚀 Features**

* **📊 Historical Event Analysis**: Pre-loaded with major market events since 2000 (e.g., 2008 Crash, Demonetization, Covid Lows).  
* **🔄 Live Data Fetching**: Automatically pulls real-time Nifty 50 price and date from Yahoo Finance (via a CORS proxy).  
* **🎛️ Interactive Filters**: Toggle between **8%, 10%, 12%, 14%, and 16%** growth projections to customize your analysis.  
* **📉 CAGR Projections**: Instantly calculates where the market *should* be today based on historical Compound Annual Growth Rates.  
* **🎨 Visual Heatmap**:  
  * \<span style="color:green"\>**Green Cells**\</span\>: Market is trading *below* the trend (Potential Value).  
  * \<span style="color:red"\>**Red Cells**\</span\>: Market is trading *above* the trend (Potential Premium).  
* **🧭 Sentiment Gauge**: A "Fear & Greed" style meter that aggregates all active projections to give a summary verdict (e.g., "Strong Buy", "Neutral", "Caution").

## **🧠 How It Works**

### **1\. The Math**

The application uses the **Compound Annual Growth Rate (CAGR)** formula to project future values:

![][image1]

| Variable | Description |
| :---- | :---- |
| **![][image2]** | Projected Price (The value in the table) |
| ![][image3] | Historical Price (Nifty level at the event date) |
| ![][image4] | Growth Rate (e.g., 0.12 for 12%) |
| ![][image5] | Time elapsed in years (Calculated precisely using days) |

### **2\. The Logic**

* **Comparison**: The app compares the **Current Live Nifty Level** against these projected values.  
* **Interpretation**:  
  * If Current Level \< Projected (e.g., 12% from 2008): **Bullish/Cheap** (Green).  
  * If Current Level \> Projected (e.g., 12% from 2008): **Bearish/Costly** (Red).

## **🛠️ Tech Stack**

* **HTML5 & Vanilla JS**: Single-file architecture. No build steps.  
* **Tailwind CSS**: Used via CDN for rapid styling and responsiveness.  
* **Yahoo Finance API**: Data fetched via corsproxy.io to bypass browser CORS restrictions.

## **📦 Installation & Usage**

Since this is a standalone HTML file, no complex installation is required.

1. **Clone or Download**:  
   git clone \[https://github.com/yourusername/nifty-valuation-tool.git\](https://github.com/yourusername/nifty-valuation-tool.git)  
   \# OR simply download the index.html file

2. **Run**:  
   Double-click index.html to open it in any modern web browser (Chrome, Firefox, Edge, Safari).

## **⚙️ Configuration**

You can easily add your own historical events by editing the events array in the index.html file:

const events \= \[  
    // Add your new event here  
    { name: "My New Event", date: "2023-01-01", nifty: 18000 },  
    // ... existing events  
\];

## **🌐 Deployment**

You can host this for free on **GitHub Pages**, **Netlify**, or **Vercel**.

### **GitHub Pages (Recommended)**

1. Rename your file to index.html.  
2. Push the code to a public GitHub repository.  
3. Go to **Settings** \> **Pages**.  
4. Under **Source**, select main branch and /root folder.  
5. Click **Save**. Your site will be live at username.github.io/repo-name.

## **⚠️ Disclaimer**

**Important**: This tool is for **educational and informational purposes only**.

It does not constitute financial advice, recommendation, or solicitation to buy or sell any securities. Stock market investments are subject to market risks. Please consult a SEBI registered financial advisor before making any investment decisions. The author is not responsible for any financial losses incurred based on this tool.

\<p align="center"\>

Made with ❤️ for the Indian Stock Market Community

\</p\>

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAmwAAAA6CAYAAAAN3QXmAAAEl0lEQVR4Xu3dTWgcZRgH8C1E8AvEjxrcTTLZRIRSUSHoQTxJD4KI0Ap+HTzqyWMEL1KkB29aUEEKPYmguVYKvYgXxR60h1wEQaV6keLFFmwx8XmSWZi+ZrOJ2U3S7e8HL5k8887Ms+1h/7wzu2m1AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA2Jqqqk7Mzs7eWtYBgPFxIN7wn5yZmXmhHNPT0+3cXx4wAgfKa9fjubqHXTU3N3dXXHuxrO+1+H861+yr3W7fHkHtu6j/E+OLvfi3AgB2Qa7MxJv9hzGu1m/8FyMU/JojtlczEJTHDFv2UF9vrYfG9f/KHiJAPVQeM0IZHt+fmpq6rdwRvTwd4/uyvluir8P571LUjkRPPzVrAMCYijf95RivNmudTmcqA1wEqteb9VFot9v3bdJDBseR95DiOp9HCDpb1D6IcTz6+C3G5ea+QeK4Z8raTkxPTz8c53yj93v0cybG2805AMCYijf9KzEOFbVDMS5FgHmrWR+FCCKPb9LD6m70kDKQlaGxJ+q/bDew5W3dsrYT9Yrot3nbNn/PnnKVrdvtPrLRqiAAMD7yObbVshi1U1nvdDr3lvuGLULH6Q16mMge8rbsVnuI4BKHVEf71I+V9aY6DJ2PXu4u96XdCGxx/pMxXsnwFT8/ip5e3mDOSm/FMba/iWu80wtwAMCYqm9HlmEpw8Da82RlfRSq9duh1/WQASt7iHDyWLM+SBxzoRnO6rB2oTlnIzFvMuYtxeZEuS9VIw5scf0n4rW+lteI8WVsPx8/fy7nRe1SjFO5vbCwcEuEu3vKOQDAmMnVmgxGGc5yxPYPMU60BnxC9ODBg3fGvAcGjdaA86SYt1r2UH/YYOCxG4kQ82Cc41iGtXh9L7a2cJ647sJmt16rEQa26LcT5z4T85+Kn9dyxSz6/jq2r5Zzo3Y+xldlHQAYU72H/Xu32PZCb4WvXw8RYhZj/ycZwnIVqtzfTxz3Yxx3pbWFsJbyObodBrb/fD1JvKb3ylqc49nJyck7yoNT7Ps0xkpZb8qwJrABwE2k97B/ri6V+wYZ1gpb3cPlfj3EvuWcU29/1upzy7LpRlth68nXGuNiWW+qrLABwM0l3viXqvVnxwYGmhHJDxYsRbA53erTQx2UMvjldt9g11PdoM+wpfy/qNZvR/dVrT/DdrKsAwBjJh9WrwPK73VIWAtEuyl7qFfXsod3+/VQB6UtBbY6nA31U6Lz8/P35/Vj/BnjWm5n7805/WwzsOWndVfimCPljqacU/X56hEAgD1RBLZcXbruu9qGKc799zDD0DYD29pt5rLWlKEyznnWd64BAPtKBKg/ut3uo/X2cn5IoZwzLBmGcpT1/2t2NH/p4KWyDgCwpyKkHa3Wb1W+mX+qqtw/ZBNxnY/34wpW9HW48ndDAYD9Kr+XbJS3QpvyWhGOFsv6XovXf24/9gUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACMsX8BW/sjD8Z08n0AAAAASUVORK5CYII=>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA0AAAAWCAYAAAAb+hYkAAAA30lEQVR4XmNgGOZAXl7eE4hnAfFcIL4AxSA2SGyWnJxcvrS0tDC6Jk2gRAiQXgrE/xUUFBJAfBgGiv0C4q8ommAAKDEJpAldHGiIB1D8H7o4A9BEJaDEcyD+hC4HFAvCZhiDrKysH0gCiE+jywHFpmDVBBRshWqag0XuGRD/QhEUFRXlAQoegGqKRpJiBrrAFij2EYg9kcRRnHZVSkpKBEUSF0By2hoglwVdHgMgOw0YtOno8lgBUlB/AzrTFF0eKwAqng112jaQrejyKEBRUVEfqPATVAMy3oOudhSgAQCTUUbosnGBvgAAAABJRU5ErkJggg==>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAAWCAYAAADNX8xBAAABf0lEQVR4Xu2TP0jDYBDFK3URBAeNYJs0TTI5Oemkm4il1EHcurg5Cg4K7u4ixaHqKC7OTg4OTgri0kkcBNFBHCzUoYL6O/wavpyRWlx98Mh3995d7vInk/lHT/B9vwTr8ABeG8pZcvVCobCaz+eHdd03YB7HvMT1EH4Ui8VliTsk14YtWNa1qcC4I410nsbz5N/hTRRFntYT4M4hxkfY1Bq5RbkBfMM3rfUEPM9bMOZLrZGricZkF12fFcYt02g/RXuAbaapaC0Bx3EGMZ6ZRlVLyjLpDLkXWLLy6bDWauRyuRGtW8jiKcNdaiIt2msdE/Zr3aCP1dbx1F3XHeB6HgTBVKzaa/EwV6zCBNADmZhJJk28CY9ig/XaXzumNPhfn8A9b801cRXe2oY9mQaeyHSxoMANN/DcwTETVzi3Muw3waFpmtg81U0EPzbqFRStpTR61r6uoHCWwifZxMQyYUP7uoKfdZTCK/mBJeZco9m29v0aYRgOMdUcx6zW/oRPVhxzB9Aa44QAAAAASUVORK5CYII=>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAWCAYAAAD9091gAAAAnUlEQVR4XmNgGAUoQFpaWhhIMWLlKyoqmsnLy98F4tNAtjqQngTEhxUUFA4xKCkp8QM5W+Tk5HyB9H8g/gTEOUC8HcRnABKeULwGiP8BFbqATAXSNjIyMiowK0EKrwLxA6CgNFwQGQAlf4NMATJZ0OXAAGQf0NhydHEwALpcHGSFlJSUCLocGAB1GgPxfAakcEAHzMbGxqzogoMFAADgACCUIS9IWgAAAABJRU5ErkJggg==>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAYAAAAYCAYAAADZEIyjAAAAu0lEQVR4XmNgGCxARkZGF4hV0MUZ5OXlnygoKCxEFwdJ/JeTkytHFwdJ/ANKuKAIAo3gAEo8ANohDRYAqsgDGYGGfzKIioryABmSQB0RQEX9ILaysrIYzCQWoMAaoIQS3GwQUFRUFAdK3AXpRpEAqrQBSvxGEQQBoGARyFIolwVkH5gBMh+I34I4QN3GQPZisBJQMAA5D5WUlPiB7FVAO83AEkBVvkCJj0B8Dog9oUZCAMhFIN+jCNIYAADEySlswQUMaAAAAABJRU5ErkJggg==>
