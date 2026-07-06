# Sales Dashboard

### Dashboard Link : https://app.powerbi.com/groups/07d46044-5225-4f0d-b56c-f4b654b2bc94/reports/f57052f2-ca6a-41e3-9e87-e600444eb7b0?experience=power-bi

## Problem Statement

This dashboard helps in Sales understand the Average Demand Per Day,Average Availability Per Day , Total Profit ,Total Supply Sortage ,Total Loss  and Average Loss  better. It helps in the Sales know if their customers satisfied with their services. Through different Areas Like More The Demand Have to maintain more Stock So That It Helps in maintaining Needs of Customer and Know Total Supply Sortage,Average Availability  they get to know their improvement area, & thus they can improve their Inventory by identifying these area. It  lets them know the average Loss & 
Average Availability, thus since by using this dashboard they have identified this problem, they can further work on These Factors

Since, Average Demand(48.65) Per Day Almost Twice than Average Availability(24.70) Per Day  Thus in all they must work on improving their services. 

Also Total Supply Sortage(61,000)  & Average Daily Loss(2970), thus they must try to reduce it.


### Steps followed 

- Step 1 : Load data into Mycrosoft sql server, dataset is a csv file.
- Step 2 : Open Mycrosoft Sql Server editor & Applying Sql Quries on Data Applying Left Join On Table To Combine Data ,Also Update Values of Data by Using Sql Quries.  
- Step 3 : Then Import Data From Mycrosoft Sql Server Transform into Power Qurie editor, This dataset contains 1019 raws 
- Step 4 : It was observed that  none of the Columns Contains
errors & empty values .
- Step 5 :  Create measures For the dataset 
- For Average Availability Per day DAX expression written below

    Average availability Per day = DIVIDE([Total availablity],[Totaldays])
- For Average Demand Per day DAX expression written below

    Avg Demand Per day = DIVIDE([Total Demand],[Totaldays])
- For Average daily Loss Per day DAX expression written below

    average daily loss = DIVIDE([Total Loss],[Totaldays])
- For Total Availability DAX expression written below

    Total availablity = SUM('Demand/Availability'[availability])
- For Total Demand DAX expression written below
 
    Total Demand = SUM('Demand/Availability'[Demand])
- For Total Profit DAX expression written below

    Total Profit = SUMX(FILTER('Demand/Availability','Demand/Availability'[Loss/Profit]>0),'Demand/Availability'[Loss/Profit]*'Demand/Availability'[Unit_Price])

- Step 6 : For the Report view,  Canva Template was Selected For Better visualizations.
- Step 7 : Making Report Source is Mycrosoft Sql Server
- Step 8 : Cards were added for First Page Of Report fields named "Average Demand Per Day", "Average Availability Per Day", "Total Supply Sortage" .
- Step 9 : Cards  were also added for Second Page Of Report fields named "Total Profit", "Total Loss", "Average Daily Loss".
           Using visual Level filter from the filters pane, basic filtering was used & Order Date  and Product Name were selected for consideration.
           
- Step 10 : Shift datasource from Mycrosoft Sql Server to My Sql by using data source setting , Same Report  created representing the same numbers on Each of Card AS well as Mesures were also same were Created by Report using MycrosoftSql Server as a datasource. Here I Changed Data Source Data were Same and number Also same The Mesures were created That is also same For both the datasource (Mycrosoft Sql Server & My Sql)

- Step 11 : Calculated column was Also Created, Loss/Profit which Represented  How  availability or demand Columns Related
if availability is greter than Demand then Profit and
if demand is more than availability then Loss.

for creating new column following DAX expression was written;
       
       Loss/Profit = [Total availablity]-[Total Demand]
        
- Step 12 : New measure was created to find total Loss.

Following DAX expression was written for the same,
        
    Total Loss = SUMX(FILTER('Demand/Availability','Demand/Availability'[Loss/Profit]<0),'Demand/Availability'[Loss/Profit]*'Demand/Availability'[Unit_Price])*(-1)
    
![Dashboard_upload]https://app.powerbi.com/onedrive/open?pbi_source=ODSPViewer&driveId=b!XdhmUvsZSUGi-H-bRu5wLDhG-I_nadlDm_syJG7kDAt46OnNBX4WRp2VbNepWI76&itemId=01ZI5GVAQPR4S5LFWASNG3FRTESB5NXQZI
# Insights

A Two page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

1. Average Demand Twice Then Average Availability Per day
2. Total Profit is Less than Total Loss
3. Total Supply Sortage
