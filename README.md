# Zone-Recovery-Trading-Bot-
A zone recovery trading bot with AI-assisted coding, designed for MetaTrader 4/5 and applicable to prop firm. The bot can trade multiple instruments, including gold, cryptocurrencies, and forex, though backtest results showed negative performance.

# Strategy and Restriction
This strategy compose with four horizontal lines from top to bottom: Top Exit, Buy Line, Sell Line, Bottom Exit.
Assume the distance from the Buy Line to the Sell Line is x; then the distance to Top Exit is 2x, and to Bottom Exit is 3x.
<img width="613" height="285" alt="image" src="https://github.com/user-attachments/assets/8448bb91-7ee7-429a-93e2-342578966470" />




- First, place a buy order on market price of x units and the price will be the Buy Line.
- If price hits Top Exit then exit.
<img width="384" height="257" alt="image" src="https://github.com/user-attachments/assets/dff4ae18-c0ad-4dfd-8457-b897f6b3db46" />
<br/>
<br/>
  
- If price hits the Sell Line then open a sell of 2x.
- If price hits Bottom Exit then close all positions (since the sell is twice the size of the buy, the sell can cover the loss of buy order).
<img width="450" height="243" alt="image" src="https://github.com/user-attachments/assets/5e28b0fd-ef77-4199-935a-84da202f0f00" />
<br/>
<br/>

- Similarly, if price returns to the (Buy Line/Sell Line), will triger a (buy/sell) order that’s double the size of the previous. Continue the cycle until price hits the Exit line, then close all positions.  
- Continue alternating (doubling each time) until an exit line is reached, at which point close everything.  

<img width="496" height="262" alt="image" src="https://github.com/user-attachments/assets/6fdfc54a-1cf4-42ad-acd2-1fa4fc8d5d20" />
<br/>
<br/>
<br/>

# Restriction
- Due to limited capital, there'll bee a maximum number of entries.
    - Once that max is reached, no further orders will be placed.
    - It might cause a loss if price moves against the final entry.
<br/>

- No weekend trading since liquidity and volume are lower.
