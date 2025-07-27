---
title: "🧰 Google Sheets Trading Dashboard: A Free Template for Equity Traders"
date: 2025-02-01 09:40:00 0100
categories: [Trading Tools]
tags: [trading-tools, google-sheets, dashboard]  #TAG names should always be lowercase separated by comma
image: 
  path: /assets/img/2025/3/TG-Dashboard-Clean.png
  lqtip: 
---


Having a clear (and aesthetically pleasing 🤩) overview of your trading portfolio is essential. It helps track open positions, manage risk, and monitor performance KPIs, keeping your trading focused and structured.

In this blog post, I’m sharing a powerful **Google Sheets template** that I put together for my [25 Year Trading Experiment](https://www.tradergu.com/posts/25YearTradingExperiment/).

## What This Dashboard Covers

This dashboard showcases a lot of data, but here are the key highlights:

- Open trades
- Entry, stop Loss, and current price
- Risk per trade
- Live current prices from index funds (e.g., **Storebrand Global All Countries A SEK**) 
- Performance comparison between portfolios or indices
- Flag emojis for geographic exposure overview 🇸🇪 🇺🇸

## How to Get the Template

1. **Open** my shared [Google Sheet Dashboard](https://dashboard.tradergu.com/)
2. **Make a copy** and edit as needed.

## How to Use the Template
![image](/assets/img/2025/3/TG-Dashboard-Markup.png)
*Google Sheets Dashboard - Cells to edit*


### Cells to Edit

- All **blue-colored** cells are the ones I edit.
- If you're unsure of your financial instrument’s ticker or exchange, check here:  [markets.ft.com/data/](https://markets.ft.com/data/)

### Portfolio Currency

- The template is based on **Swedish SEK** but can easily be adjusted to your local currency.
- Just tweak the formulas in the **current price** cell and update the cell formatting accordingly.

### Advanced: Fetching Current Prices Using ISIN


[Google Finance](https://support.google.com/docs/answer/3093281?hl=en) is a powerful Sheets tool, but it has limitations when fetching certain financial instruments like mutual funds or ETFs. Luckily, someone smarter than me figured out a way to **track current prices using ISIN numbers** with a custom Google Apps Script.



> Big shout-out to the author of [this blog post](https://kollpakontot.blogspot.com/2024/10/indexfonders-nav-kurs-i-google-sheets.html) where I first found this method—it’s something I’ve wanted for months. 🙌 ☕️
{: .prompt-tip }  


### Here's how you can integrate it into your Google Sheet:

#### **Step 1**: Open Extensions setting in your Google Sheet and press Apps Scripts.

#### **Step 2**: Remove any code and replace with below script.

```text
function fintime1(symbol) {

  symbol = symbol || "IE00BF20L762:SGD";
  
  symbol = encodeURI(symbol);
  Utilities.sleep(Math.floor(Math.random() * 5000));
  
  var url = 'https://markets.ft.com/data/etfs/tearsheet/summary?s=' + symbol;
  Logger.log(url);

  // Fetch the URL
  var response = UrlFetchApp.fetch(url, {muteHttpExceptions: true});
  var responseCode = response.getResponseCode();
  
  if (responseCode === 200) {
    var html = response.getContentText();

    // Use a regex that captures numbers, including commas and periods.
    var match = html.match(/<span class="mod-ui-data-list__value">([\d,\.]+).*?<\/span>/);
    
    if (match && match[1]) {
      var content = match[1];  // The captured group with the number string
      var finContent = content.toString().replace(/,/g, '');  // Remove commas from the number
      Logger.log(finContent);  // Log the cleaned-up number
      
      return Number(finContent);  // Convert the cleaned-up string to a number and return
    } else {
      Logger.log("No match found for the number.");
      return null;
    }
  } else {
    Logger.log("Failed to fetch data. Response Code: " + responseCode);
    return null;
  }
}
```

#### **Step 3**: Click **New Deployment** and **Select type**, Web app

#### **Step 4**: Choose a Description (optional), and select Who shall have access and click **Deploy**

#### **Step 5**: Done!
Now, try it out by calling the function below in your Google Sheet.

`=fintime1("SE0000671919:SEK")`


## Bonus: Want to Improve This?

Let me know how this template works for you! If you have suggestions for improvements, feel free to connect and reach out to me on [x.com/tradergu](https://x.com/trader_gu).


> If anyone manages to **revise this script** to also fetch **name, and currency**, please let me know. 👀
{: .prompt-tip }


---

## FAQ

**Q: Do I need a Google account to use this template?**  
A: Yes, you'll need a Google account to make a copy of the sheet.

**Q: Will the script work with all financial instruments?**  
A: It works for most ISIN-based instruments but might not support all assets.

**Q: Can I modify the script to fetch additional data?**  
A: Yes! You can tweak the script to retrieve more details like historical prices or volume if needed.

**Q: How can I change the template currency?**  
A: Update the formulas in the current price cell and adjust the cell formatting to match your preferred currency.

<script src="https://giscus.app/client.js"
        data-repo="tradergu/tradergu.github.io-comments"
        data-repo-id="R_kgDOOJkYuA"
        data-category="General"
        data-category-id="DIC_kwDOOJkYuM4CoG-6"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="top"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
