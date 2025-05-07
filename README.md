# Netflix-Azure-Data-Engineering-Project

## Data Sources
<link> https://public.tableau.com/app/learn/sample-data </link>
<br>
https://www.kaggle.com/datasets/shivamb/netflix-shows

### Establish a pipeline to ingest the data into the data lake at the bronze layer from GitHub using the API with the help of Azure Data Factory.
#### Create two Linked Services between GitHub and Azure datafactory, and Azure Datafactory and Azure Datalake Gen2
<img width="1268" alt="image" src="https://github.com/user-attachments/assets/349bfd0f-fb40-409b-a2eb-faad9b5773cf" />
#### Create Copy data Activity: 
<img width="477" alt="image" src="https://github.com/user-attachments/assets/9955bb6a-8a59-44f6-babf-6599cbf73b2e" />
<img width="583" alt="image" src="https://github.com/user-attachments/assets/905a5c1f-0742-4f71-a16e-4dda279936e3" />
<img width="605" alt="image" src="https://github.com/user-attachments/assets/f62346cf-fa0c-4600-94da-769fd2f6421f" />
#### Create a ForEach Activity to pass parameters in the form of an Array containing the folder and file names.
<img width="417" alt="image" src="https://github.com/user-attachments/assets/b27df263-7fcf-4418-9805-ff946613d882" />
<img width="487" alt="image" src="https://github.com/user-attachments/assets/10242a4b-457a-45f7-a5ff-9570b8367f1c" />
#### Create a Validation Activity that checks for title files in the Raw container. This is a validation run before the "For each" activity, which has a "Copy Data" activity embedded.
<img width="496" alt="image" src="https://github.com/user-attachments/assets/41e1cc75-3235-43ce-8818-272c7b03242c" />
<img width="448" alt="image" src="https://github.com/user-attachments/assets/bbbe87bb-cff4-423c-936e-03e76187d868" />







