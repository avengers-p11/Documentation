
| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 11-12-24           |  | | |   




## Proof of Concept: FOSSA

1. Pre-requisites

    Access to FOSSA:    
        Sign up for a FOSSA account if you don’t have one.
        Access to the FOSSA dashboard and API token.
   
    Project Repository:             
        Ensure the project source code is hosted on a supported version control system (GitHub, GitLab, Bitbucket, etc.).
   
    System Requirements:
        FOSSA CLI installed:

   Access to the internet from your development environment.

2. Setup and Configuration

    Install FOSSA CLI:
        Use npm to install the CLI globally.
```
    npm install -g fossa-cli
```
![Screenshot from 2024-12-12 12-43-58](https://github.com/user-attachments/assets/930026a8-cb83-492a-a5c5-863f0afce522)

Authenticate the CLI:

   Obtain an API token from the FOSSA dashboard: Settings → API Keys.
   Authenticate the CLI using the token:


```
        fossa login --token <your-api-token>
```
  ![Screenshot from 2024-12-12 12-42-53](https://github.com/user-attachments/assets/d1d6a5db-8ec3-4809-85da-4eafa0cfbf00)

3. Integrate License Scanning in the Project

    Initialize FOSSA in the Project:
        Navigate to the project directory and initialize FOSSA:
```
    fossa init
```
  ![Screenshot from 2024-12-12 12-43-22](https://github.com/user-attachments/assets/cc25f00a-10eb-411c-933a-1f88a73d3edc)

   This will create a .fossa.yml file with default configurations.

Edit .fossa.yml (Optional):

  Modify the .fossa.yml file if needed to include/exclude specific paths or dependencies.

Run FOSSA Analysis Locally:

  Execute the CLI to analyze your project dependencies:
```
fossa analyze
```

![Screenshot from 2024-12-12 12-38-49](https://github.com/user-attachments/assets/3260c4bd-eb57-46b6-82c8-a4630761d89b)

Review the analysis results in your terminal or the FOSSA dashboard.
![Screenshot from 2024-12-12 12-37-48](https://github.com/user-attachments/assets/9ff1c51f-88e3-439c-9e4b-7d7369a850d9)







