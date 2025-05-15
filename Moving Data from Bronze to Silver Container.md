# Copying data from bronze layer to Silver layer using lookup Table via workflows
#### Before performing Operation:
**Silver Container:**
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/eebf739a-ee00-4d1a-b09d-8995b6393c5f" />
**Bronze Container:**
<img width="1276" alt="image" src="https://github.com/user-attachments/assets/0bf3c06b-5a76-487d-8562-e982fbaba524" />

## 1. Notebook1: Creating parameterized notebook that accepts target and source folder name as inputs.
<img width="911" alt="image" src="https://github.com/user-attachments/assets/52c3e90f-417b-48ce-b434-224aea6abb4f" />

## 2. Notebook2: Create an array that contains all folder names that needs to be copied from bronze container to the silver container.
## As this array value needs to be used in another notebook, we use dbutils.jobs.taskValues.set(key = "any_name",value="array name_created for use in another notebook")
<img width="930" alt="image" src="https://github.com/user-attachments/assets/e3182d21-4825-4db9-b3bf-2651c1a070a5" />

## 3. Create a Workflow to accept the array value of Notebook1 and pass it to the Notebook2.
### Step 1: Create a new job.
### Step 2: Create a task1, that is to accepet the lookup_Notebook that contains the array whose value is folder names that needs to be copied from bronze to silver container.
 **Select the values**
 <img width="1093" alt="image" src="https://github.com/user-attachments/assets/3fd5b05b-f547-44a6-8234-05f9ac5fe010" />
 <br> **After creation of Task**
 <img width="1097" alt="image" src="https://github.com/user-attachments/assets/53995be7-ae0b-40e6-ab9b-c9a319965c84" />
### Step3: Add a task to task 1.
<img width="716" alt="image" src="https://github.com/user-attachments/assets/c5e92249-437d-4ac9-ac1f-70acc26de925" />
**Successfully created the two tasks**
<img width="731" alt="image" src="https://github.com/user-attachments/assets/cbe4a382-7d38-4733-b2bf-7775018d96bd" />
### Step4: As the parameter is an array, we need to access each element of the array, hence we use For Each Activity for the SilverNotebook
**Click on the Task 2, and select the loop icon and configure the values as shown below:**
<img width="731" alt="image" src="https://github.com/user-attachments/assets/89ccc8d2-b40e-4f78-b0e5-b12565981599" />
**Click on the inner-book that is the Silver Notebbok and provide the parameter value as shown below:**
<img width="734" alt="image" src="https://github.com/user-attachments/assets/5b18539f-4311-4c7a-95e7-dd8f3aa81a52" />
### Pipeline Created Successfully
<img width="1130" alt="image" src="https://github.com/user-attachments/assets/6dfeb009-5073-47f4-a476-2fbad966ab89" />
### Step5: Run the Pipeline.
<img width="1125" alt="image" src="https://github.com/user-attachments/assets/f5c708bc-dcd0-4fef-82b0-ae5c9d8c399b" />
### Step6: Exceuted Succesfully
<img width="1121" alt="image" src="https://github.com/user-attachments/assets/506aff45-aadf-4882-862b-e38ed26fa1f3" />

#### After performing Operation:
**Silver Container:**
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/29e7ec39-0a2d-430e-aa81-1f61a0d5c441" />







