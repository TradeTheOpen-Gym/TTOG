# Trade the Open - Gym

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

## Description
The belief that 10,000 hours of practice are necessary to achieve proficiency in any field is widely popularized. In the realm of active intra-day trading, many market participants consider the first two hours of the trading day as the most viable period due to higher volatility, which diminishes later in the day. Given that there are about 250 trading days a year, it could take up to 20 years of study during market hours to reach the 10,000-hour mark. Therefore, alternative methods to expedite this learning process are highly sought after.

'Trade the Open - Gym' (TTOG) is a free software designed to address this need. TTOG allows users to replay historical price action and practice intra-day trading. By using ticks of Ask and Bid prices, TTOG aims to simulate price movements that closely resemble real-time market conditions. While creating a perfect simulation may be virtually impossible, potential users can evaluate for themselves whether the quality of the simulation is sufficient for their practice needs.
## Disclaimer
'Trade the Open - Gym' is a simulated trading environment designed for educational purposes only. It does not reflect critical market conditions
such as market depth, liquidity, or differences in order execution properties depending on varying market volatility. Success in this simulator
does not guarantee similar results in real trading scenarios. Past performance is not indicative of future results. By using 'Trade the Open - Gym',
you acknowledge and agree that:
1) You are solely responsible for your trading decisions and outcomes.
2) 'Trade the Open - Gym' and its affiliates are not liable for any losses or damages arising from your use of this simulator.
3) This software is provided 'as is,' without any warranty of any kind, express or implied.
4) You understand the limitations of simulated trading and the differences from real trading.
## How to?
Download the most recent 'Trade the Open - Gym' files archive (TTOG_vX.X.X.X_XXXXXXXX.zip where the X denote version numbers and date) from the Releases section on the right and extract it to your preferred location. Then, follow the instructions below to set up 'Trade the Open - Gym' (TTOG).
<details>
  <summary>
    Click to expand - <b>Installing Python and Visual Studio Code</b>
  </summary>

  `We'll be downloading tick historical price data for use with TTOG from Dukascopy via a Python script. If you don't have Python and Jupyter notebooks set up, refer to the instructions below. You don't need to be a programmer; if you can click a mouse and press keys on a keyboard, you'll be able to complete all these steps.`
  
  ### Steps to follow:
  
  1) Search for ‘Microsoft Store’ in the Windows taskbar, and click to open it.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/53194b5b-48d7-4253-b873-3aba964c67e5" style="width: 70%;"/>
  2) In Microsoft Store, search for ‘Python’, select the first result, and click ‘Get’.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/8b21705b-348c-453a-a37f-2bbdfacf3dfa" style="width: 70%;"/>
  3) Once the download and installation are complete, ignore the pop-up suggesting you launch Python or pin it to the desktop. Instead, search for ‘Visual Studio Code’ in Microsoft Store. Select the app and click ‘Install’.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/c9c53611-2a55-4472-805d-dbe8e6850bfa" style="width: 70%;"/>
  4) After the installation is complete, search for ‘Visual Studio Code’ in the Windows taskbar and click to start the program.
  5) When the program opens, click on the ‘Extensions’ tab (the symbol with four squares on the left), then search for and install both the ‘Python’ and ‘Jupyter’ extensions.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/c76ac083-3597-4de5-9ce6-5e4628d270e2" style="width: 100%;"/>
     <br>Once the extensions are installed, click the four squares symbol again to hide the extensions marketplace.
  6) Now, let's install some Python packages that we will be using. Search for ‘cmd’ in the desktop search bar, and click the ‘Command Prompt’ app.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/0b601923-7732-433b-aad8-cb96f4ffc0c9" style="width: 70%;"/>
     <br>In the command prompt, type or copy/paste the following and hit ‘Enter’:<br>
     `pip install ipykernel numpy pandas pillow pyautogui matplotlib mplfinance --no-warn-script-location`<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/332fee59-9831-4334-9cb7-0ad86f6a0dbe" style="width: 100%;"/>
     <br>Wait for the packages to finish installing. The process is complete once you see a blinking cursor again.
  7) Now it’s time to test the installation. Open the Visual Studio Code window again, click on ‘File -> New File…’ and select ‘Jupyter Notebook’ from the dropdown menu.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/ae6a14e5-67a3-497f-819b-b45019778a6b" style="width: 100%;"/><br>
     This will open a new Jupyter notebook tab (a .ipynb file).<br>
     Type 1+1 in the top cell of the notebook and hit ‘Ctrl + Enter’.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/48b4bad5-f35e-4726-84b5-933b2ac30031" style="width: 70%;"/><br>
     At this point, Windows might ask for permission for Visual Studio Code to access the internet. Don’t worry, the app is developed by Microsoft and is safe. Click ‘Allow access’.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/4f479de2-5e26-43b4-9e9c-dad0d23bad1b" style="width: 70%;"/><br>
     If the cell shows a green checkmark and the correct answer ‘2’ appears below it, everything is set up correctly.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/7a09c48a-b5e8-49e6-a357-c77150461ef1" style="width: 70%;"/>
</details>

<details>
  <summary>
    Click to expand - <b>Downloading tick historical price data from Dukascopy</b>
  </summary>

  `To enable the mouse-click automation steps used in this section, you will need to move the Windows taskbar to the vertical position on the right side of your screen. If you are using Windows 11 with the taskbar fixed at the bottom, please follow the 'How to?' section under the following link` https://github.com/valinet/ExplorerPatcher `to recover the Windows 10 taskbar style on your machine.`

  ### Steps to follow:
  
  1) Right-click the empty space on your desktop and select 'Display settings'. In the settings window that opens, scroll down and ensure that your Display resolution is set to 1920x1080 and Scale is set to 100%. (You can change it back once we are done with the download steps in this section.)<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/cee84743-0bcc-47e4-bb3b-f2b72ff6ae6f" style="width: 100%;"/>
  2) Right-click the empty space on your taskbar and make sure that 'Lock all taskbars' is not checked. Then, grab the empty space on your taskbar by clicking and holding the left mouse button and drag it to the right edge of your screen, so that it is now standing up vertically.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/e4f0f26a-fd10-4c8f-a627-e96e931e3fe4" style="width: 70%;"/>
  3) Open a web browser (e.g., Chrome) and make sure that it is maximized to fill the entire screen and set to the standard 100% zoom scale. Hold the 'Ctrl' button on your keyboard and scroll the mouse wheel up or down until the zoom level is set to 100%.
  4) In your browser, load the page: [Dukascopy Historical Data Feed](https://www.dukascopy.com/trading-tools/widgets/quotes/historical_data_feed). Click on the search bar around the center of the page (it initially says 'Instrument') and search for the symbol you would like to download data for. For example, we will search for the `SPY` ETF symbol. Then, click on one of the search results below the red line to select it.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/d995d17e-d967-49f7-9bf9-9a2407465785" style="width: 100%;"/>
  5) Scroll down just a bit until you see the black 'Download' button below. Make sure that you do not scroll too far. When you click on the date entry field, the calendar pop-up needs to exactly touch the bottom of your screen (not hover above or be hidden from view). It will snap to this position automatically if you have not scrolled too far when clicking on the date entry field.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/20cdbe37-c83e-4e1d-8968-d056d1bf71c2" style="width: 100%;"/>
  6) Select the earliest date you would like to get data for, and click the black 'Download' button. Usually, data goes back several years. You can find the earliest available date by selecting a random date from, e.g., 20 years ago, which will cause the calendar to default to the earliest available date.
  7) Read the 'Disclaimer'. If it does not disqualify you based on your affiliations and/or professional occupation, click 'Accept'. (If it does disqualify you, you will not be able to acquire data this way.)
  8) In the next pop-up, log in with your free account, or create one and then log in.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/3b2886ad-e560-4eb5-af5b-4ce2c2cfffe5" style="width: 50%;"/>
  9) If login is successful, after a brief loading animation, you should see the following at the bottom of your screen:<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/b258fd37-d7e9-4ff0-be54-cb8a452d9764" style="width: 70%;"/>
  10) Start Visual Studio Code, click on 'File -> Open File', navigate to the folder where you extracted the 'Trade the Open - Gym' files, select the file 'dukascopy_data_pull.ipynb', and click 'Open'.
  11) Make sure the bottom portion of your browser window is still visible on the screen in the background and Visual Studio Code is only occupying the top portion. Click anywhere in the first cell of the 'dukascopy_data_pull.ipynb' notebook and hit 'Ctrl + Enter'. If you properly adjusted the screen resolution, taskbar position, browser scale, and scrolling position on the web page, you should see the following output below the first cell in the notebook:<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/de3a3a7d-598a-4ff2-8d4d-40a7cec98143" style="width: 50%;"/>
  12) If the output looks correct, click anywhere in the second cell of the notebook and hit 'Ctrl + Enter'. Then, return to the Dukascopy browser window, click the 'Save' button at the bottom, then the 'Reset' button at the bottom right, and subsequently the calendar field to select the next date. At some point during these actions, the Python script running in the notebook will pick up your mouse cursor and start performing these actions automatically. It will select subsequent dates and download the respective files by itself until the last available date has been reached. Do not touch the mouse and do not use your computer during this process.
  13) Sometimes, the Dukascopy page refreshes randomly, which interferes with the automated process. When that happens, switch to Visual Studio Code and hit the 'Restart' button at the top. (Confirm the reset if it asks for confirmation in a pop-up.) <br>
    <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/3922911d-a7f9-49e4-86af-eb5bc6c3958c" style="width: 50%;"/><br>
    Then open your download folder and find the historical date in the name of the most recently downloaded file. Subsequently, start over from step 4) above, only this time select the date following the most recently downloaded file's date in step 6) instead of a date from 20 years ago. You'll skip step 10), as Visual Studio Code and the notebook are already open.
  14) You will likely have to repeat step 13) a few times before all the data downloads are complete. Bring a book to read or similar, but glance at the computer screen occasionally to see if you need to repeat step 13).
  15) Once all downloads are done for a particular symbol, create a folder with the symbol's name inside the directory where you extracted the 'Trade the Open - Gym' files (e.g., SPY for this example), and move all of the downloaded data files from the downloads folder into this new folder. In File Explorer, select 'View -> Details' to see a list view of your files, and click on the 'Size' column name at the top to sort the files by size. There may be several 0 Kb files at the top - delete them (these files correspond to market holidays on which no trading occurred and no data was recorded).
  16) Repeat the above steps for any number of symbols you are interested in and can find on Dukascopy.
</details>

<details>
  <summary>
    Click to expand - <b>Checking that data for all symbols is matching</b>
  </summary>

  `If you have downloaded tick historical market data for more than one symbol and intend to use all of them during the same 'Trade the Open - Gym' run, you have to make sure that the data for all symbols contains exactly the same dates. See how to do that below.`

  ### Steps to follow:
  
  1) Start Visual Studio Code, click on 'File -> Open File', navigate to the folder you extracted the 'Trade the Open - Gym' files into, select the file 'match_data.ipynb' and click 'Open'.
  2) In the first cell of the notebook, type a comma separated list of the folder names (enclosed in single quotation marks) in which you have placed the data for each symbol respectively. (These folders must be located in the same directory as this notebook file 'match_data.ipynb'.) Then, make sure the first cell of the notebook is selected and hit 'Ctrl + Enter'. For example, for `SPY` and `QQQ` symbols we should have used the symbols themselves as folder names, so that we have:<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/8abb0806-842d-4678-b89c-c49b94a4898b" style="width: 70%;"/>
  3) Subsequently, click anywhere in the second cell of the notebook and hit 'Ctrl + Enter'. This will compare all file names in all data folders you listed and determine if any of the dates are missing:<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/0831d983-a19e-4b09-9752-4fdc800b86fc" style="width: 100%;"/>
  4) In case if data for some symbols and dates is missing, you can revisit the Dukascopy page https://www.dukascopy.com/trading-tools/widgets/quotes/historical_data_feed , locate the missing days for the respective symbols, download them and add them to the appropriate folders. However, sometimes different symbols have different earliest starting dates of data in Dukascopy. In that case you have to delete the excess data for symbols with longer history, to make sure that all symbols have historical data of the same length.
</details>

<details>
  <summary>
    Click to expand - <b>(Optional) Adjust ETF price data to lower priced equivalents</b>
  </summary>

  `Main ETFs such as SPY or QQQ typically have high prices per share, so short-term traders often prefer to trade their lower-priced and leveraged equivalents such as SPXL or TQQQ. While Dukascopy does not provide data for SPXL or TQQQ, SPY and QQQ data can be converted to match the price action of their lower-priced equivalents. Below are instructions for converting QQQ data to TQQQ. To do the same for other pairs, such as SPY and SPXL, simply replace QQQ with SPY and TQQQ with SPXL in these steps.`

  ### Steps to follow:
  
  1) Assuming you already have a 'QQQ' folder in your 'Trade the Open - Gym' directory containing all the QQQ data files downloaded from Dukascopy, copy and paste the 'QQQ' folder into the same directory to duplicate the files and rename the resulting 'QQQ - Copy' folder to 'TQQQ'.
  2) Open your browser and go to finance.yahoo.com, search for 'TQQQ' at the top, and load that symbol's page. Then, click on the 'Historical Data' tab.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/df3035b4-1886-4145-b19c-e2ae4941b7f0" style="width: 70%;"/>
  3) In the 'Historical Data' tab, click on the blue arrow next to the 'Time Period' field, select 'Max', and then click on the blue 'Apply' button. Ensure the 'Time Period' field shows a date range longer than 1 year. If it does not, repeat the steps until it does. Finally, click on the 'Download' button.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/47205970-09f3-465f-9b85-d1de2e44ff2f" style="width: 100%;"/>
  4) Next, click on the blue arrow next to the 'Show' field, select 'Stock Splits', and click on the blue 'Apply' button. Then, click on the 'Download' button. (TQQQ will have several splits listed. If you are looking at a different symbol with no split history, still do not skip any of these steps.)<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/a72fb3a9-1c83-417c-90b7-acbeaa7b4e85" style="width: 100%;"/>
  5) Move the downloaded files 'TQQQ.csv' (daily price history) and 'TQQQ (1).csv' (split history) from your 'Downloads' folder into your 'Trade the Open - Gym' directory. Rename 'TQQQ.csv' to 'TQQQ_yahoo.csv' and 'TQQQ (1).csv' to 'TQQQ_splits.csv'. Now, the 'TQQQ' folder with QQQ symbol data, 'TQQQ_yahoo.csv', 'TQQQ_splits.csv', and 'price_adjustment.ipynb' should be in the 'Trade the Open - Gym' directory.
  6) Start Visual Studio Code, click on 'File -> Open File', navigate to the 'Trade the Open - Gym' directory, select the notebook file 'price_adjustment.ipynb', and click 'Open'.
  7) Ensure the top cell in the notebook has the correct entries for your symbol of interest, in this example price_file='TQQQ_yahoo.csv' and split_file='TQQQ_splits.csv'. (Replace 'TQQQ' with another symbol if needed, keeping all other characters the same.) Click anywhere in the first cell and hit 'Ctrl + Enter'. A green checkmark should appear in the bottom left corner of the cell.<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/cfa05805-6132-47fe-bb5a-419ce11669c4" style="width: 70%;"/>
  8) Next, click anywhere in the second cell of the notebook and hit 'Ctrl + Enter'. The cell will process your files, indicated by a rotating circle in the bottom left corner. This may take a few minutes, but once the circle turns into a green checkmark, the process is complete. Even though the files inside the 'TQQQ' folder still have 'QQQ' in their names, they now contain 'TQQQ' price information.
</details>

<details>
  <summary>
    Click to expand - <b>Converting historical tick price data to binary</b>
  </summary>

  `Historical tick price data from Dukascopy is originally stored in daily CSV files. Storing numbers in plain text like this is inefficient, takes up a lot of hard drive space, and can take a long time to load into RAM. Therefore, in this section, we'll convert the raw data into a single binary file per symbol. This will ensure that 'Trade the Open - Gym' can load several years' worth of tick data in just a few seconds whenever we start the program.`

  ### Steps to follow:
  
  1) Navigate to your 'Trade the Open - Gym' directory and double-click the file 'create_binary.exe' to start it.
  2) A Command Prompt window will open and ask you to enter the path containing data for the symbol you would like to create a binary file for. For example, if `C:\TTOG\` is the directory where you extracted the 'Trade the Open - Gym' files and it contains Dukascopy data for the symbol SPY in the sub-folder SPY, enter `C:\TTOG\SPY` into the Command Prompt window and hit 'Enter'.
  3) Next, the Command Prompt will ask you to specify a name for the binary output file. 'Trade the Open - Gym' uses a special file format with the .ttog extension. You can simply type in the name SPY here and hit 'Enter', and the proper extension will be appended automatically.
  4) The Command Prompt will then ask you for the path of the directory to save the binary output file to. You can choose any path you like. For example, you can type in the same directory `C:\TTOG\` and hit 'Enter'.
  5) Next, the Command Prompt will ask you to specify the start year for your data. This can be the first year you have data from. However, sometimes early data can be less useful, so you may want to focus on more recent years. Whichever year you choose, make sure you use the same year for the binary data conversion of all the symbols you intend to load simultaneously in 'Trade the Open - Gym'.
  6) The Command Prompt will then ask you to specify the end year for your data. This can be the last year you have data from. Again, make sure you use the same year for the binary data conversion of all the symbols you intend to load simultaneously in 'Trade the Open - Gym'.
  7) After entering the above inputs, 'create_binary.exe' will proceed to open the Dukascopy data for all days in the specified year range and save the contents in the binary file.
  8) Repeat steps 1 through 7 for each symbol you wish to use in 'Trade the Open - Gym'.
</details>

<details>
  <summary>
    Click to expand - <b>Using 'Trade the Open - Gym'</b>
  </summary>

  `Familiarize yourself with the 'config.txt' file in the 'Trade the Open - Gym' directory. In this file, you should edit the path for the binary data files you want to load. You can also set hot-keys and other settings here.`

  ### Steps to follow:
  
  1) Navigate to your 'Trade the Open - Gym' directory and double-click the file 'Trade the Open - Gym.exe' to start it. At the start, it will load the binary data files you specified in 'config.txt'. The graphical interface will then boot up, starting on the disclaimer screen.
  2) Be sure to read and understand the disclaimer completely. If you wish to accept the disclaimer and proceed, hit 'Enter'. If you wish to decline the disclaimer and quit the application, hit 'Alt + F4'.
  3) Assuming you accepted the disclaimer in the previous step, the graphical interface will load data at the market open for a random date and random ticker symbol, and then go into the paused state. In the 8 charts mode, the 4 top charts show price data of the symbol being traded, while the 4 bottom charts show the price data of your reference symbol that is not being traded (like `SPY` for the overall market). In the 7 charts mode, the top 4 and the wide middle chart at the bottom show price data of the symbol being traded, while the bottom left and bottom right charts show price data of your reference symbol that is not being traded.
  4) Hit the pause toggle hot-key to unpause the program and start the trading day (Down-Arrow is the default pause button, but you can adjust that in 'config.txt' before starting 'Trade the Open - Gym').
  5) Hit 'd' or 's' to buy or sell 1 lot (100 shares), and 'e' or 'w' to buy or sell 2 lots or close out open positions entirely. These keys can also be adjusted in 'config.txt'.
  6) Hit 'Enter' to load a new random ticker symbol and trading day. This hot-key can also be adjusted in 'config.txt'.
  7) When you do not have any trades open, you can speed up the clock in 'Trade the Open - Gym', e.g., to fast-forward over a boring part of the price action. The default hot-key for this is: press-and-hold Right-Arrow. (This functionality is disabled when a trade is open to simulate the appropriate passage of time during a trade.)
  8) You can toggle between the four different available chart modes. The default hot-key for this is Up-Arrow.
</details>

<details>
  <summary>
    Click to expand - <b>Evaluating your performance</b>
  </summary>

  `Every time you place a trade in 'Trade the Open - Gym', the program saves the trade's outcome into a file in the main directory. Over time, using 'Trade the Open - Gym', you will accumulate a sufficient trade history to evaluate your performance. See the instructions below.`

  ### Steps to follow:
  
  1) Start Visual Studio Code, click on 'File -> Open File', navigate to the 'Trade the Open - Gym' directory, select the notebook file 'evaluate_performance.ipynb', and click 'Open'.
  2) Click on the first cell in the notebook and hit 'Ctrl + Enter'. Scroll down to see a cell output of the following form:<br>
     <img src="https://github.com/TradeTheOpen-Gym/TTOG/assets/172998635/a47f8082-7876-4dad-81e0-a7bef43f8a5a" style="width: 100%;"/><br>
     Every candle on this chart represents one completed trade. The Open of each candle corresponds to the Profit-and-Loss (PnL) value before the trade, the High represents the highest open PnL during the trade, the Low represents the lowest open PnL during the trade, and the Close represents the final PnL value at which the trade was completed. Each lot transacted during the trade is independently accounted for.
</details>

## Showing Support
Do you like this project and want to support its creator? <br>
You can 'buy me a coffee': https://buymeacoffee.com/tradetheopen.gym

## License
This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International License. See the [LICENSE](LICENSE) file for details.
