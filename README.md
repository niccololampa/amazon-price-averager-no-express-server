# price-averager (no express/node server version ) 

This version of the extension will only utilize the Chrome to scrape amazon prices for a product's average price. 

However Cross Domain - CORS extension needs to be installed to disable Chrome's CORS Validation (See more details below). 

See **WITH** express/node server version [here](https://github.com/niccololampa/price-averager/tree/feature/price-averager-with-node-server)


## Setup 

### Installing Extension on Chrome 

Create a zip file of the build (based on the requirement of the project) 

```
cd app
npm run zip
```

Go to the root of the project unzip the produced file. 

![Screen Shot 2022-10-24 at 3 05 39 PM](https://user-images.githubusercontent.com/37615906/197467214-1de68c1d-83b6-4ba3-bc97-7104eefaf5d3.png)


Go to Chrome > Manage Extensions 

![Screen Shot 2022-10-24 at 3 02 39 PM](https://user-images.githubusercontent.com/37615906/197466724-e3dfab62-2794-490d-9a26-cb9b1a06201e.png)

Activate Developer Mode 

![Screen Shot 2022-10-24 at 3 03 29 PM](https://user-images.githubusercontent.com/37615906/197466837-6a99d2b0-5780-4838-920b-6c3990884307.png)

Go to Load unpacked 

![Screen Shot 2022-10-24 at 3 06 31 PM](https://user-images.githubusercontent.com/37615906/197467351-c71e2baf-8bb6-4f0f-98ea-4fcf016d33f5.png)

Then select the unzipped price averager build folder: 

![Screen Shot 2022-10-24 at 3 06 18 PM](https://user-images.githubusercontent.com/37615906/197467451-f1a09b2d-9f16-4517-9d93-411fca47e498.png)

![Screen Shot 2022-10-24 at 3 07 59 PM](https://user-images.githubusercontent.com/37615906/197467570-5443857c-f70c-4af7-a51a-4d7d8c507255.png)

Pin the extension 

![Screen Shot 2022-10-24 at 3 09 03 PM](https://user-images.githubusercontent.com/37615906/197467751-38d362aa-74e3-43eb-a6dc-e5cfc41f2473.png)


### Disabling Chrome's CORS Policy

Since Chrome validates CORS Policy and we don't have control amazon server we will have to disable the validation. 

Without disabling CORS Policy validation the extension will not be able to request data from the Amazon Server: 
![Screen Shot 2022-10-22 at 10 06 27 PM](https://user-images.githubusercontent.com/37615906/197464740-6d3bb123-e0fe-45b2-9ed9-b956a3e97f14.png)

To disable CORS validation please install the following extension in the your Chrome Browser and activate before using the Price Averager extension: 


https://chrome.google.com/webstore/detail/cross-domain-cors/mjhpgnbimicffchbodmgfnemoghjakai


![Screen Shot 2022-10-24 at 2 52 50 PM](https://user-images.githubusercontent.com/37615906/197465502-f529d43e-dc76-485c-99c2-93580876b203.png)


## Searching for average price 

Once the CORS has been disabled we can use the extension to search for average prices. 

Click the Enable button in the Cross-Domain-Cors extension:

![Screen Shot 2022-10-24 at 3 11 42 PM](https://user-images.githubusercontent.com/37615906/197468123-7196aacf-fc01-4dff-9b1b-cc97ac803415.png)

Click on the Average Price extension, then type the item name you want scrape. 

Also insert the number of pages you want to scrape (default: 1 page - top results) 

Examples: 

`pencil` (sold as a pack)

![Screen Shot 2022-10-24 at 3 13 56 PM](https://user-images.githubusercontent.com/37615906/197468506-02d8596c-fc8f-479c-a0cc-58f452da2242.png)

`shoes`

![Screen Shot 2022-10-24 at 3 23 26 PM](https://user-images.githubusercontent.com/37615906/197470080-f9f1427f-038a-439b-908b-e08b2f3ee556.png)


## Notes: 

1. The extension removes the price outliers before computing the average (see [helpers.ts](https://github.com/niccololampa/price-averager/blob/feature/price-averager-no-node-server/app/src/helper.tsx#L52-L68) file). This is to have a more accurate price average. 
2. **As much as possible do not spam Amazon with requests. Wait for a little bit rather than doing consecutive requests.  Amazon tends to block search page requests if it detects abnormal usage. And will result in the extension not being able to request prices for hours.**










