|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  13 Jan 2024  |  Version 1 | Khushi Malhotra  | 13 Jan 2024    |
***

# Declarative Pipeline-Commit SIgn-off
This refers to a way of defining automated workflows (pipelines) using code that describes the desired state of the system, rather than specific instructions on how to achieve it.
In software development, a commit represents a snapshot of changes made to code files in a version control system like Git. This usually refers to a process where a developer indicates they have reviewed and approved the changes in a commit.

# Pre-requisites
| Item         | Version   |
|--------------|-----------|
| Jenkins      | 2.426.3   |

# Commit Sign-off Setup
**Step-1** Create a New Pipeline Job

- Navigate to the Jenkins dashboard and click on New Item.
- Enter a name for your job (e.g., "Declarative Pipeline-Commit SIgn-off").
- Select Pipeline and click OK.

**Step-2** Configure Pipeline Script

- In the job configuration page, scroll down to the Pipeline section.
- Select Pipeline script from SCM.
- Give required repo url and enter your credentials.

![WhatsApp Image 2024-02-13 at 14 46 01_5dabb58d](https://github.com/avengers-p7/Documentation/assets/156056460/042d872f-31bb-4c0e-bb0f-27bb1929cf11)

**Step-3** Save the Configuration

- Click on Save to save the job configuration.

**Step-4** Build the Pipeline

- Once the pipeline configuration is saved, you can manually trigger the build by clicking on Build Now.

**Step-5** View Build Console Output

- After triggering the build, you can view the progress and console output of the build by clicking on the build number in the Jenkins dashboard.
- The console output will display the steps executed by the pipeline script, including code checkout and compilation.
- Verify Successful Compilation

![WhatsApp Image 2024-02-13 at 14 47 44_f8ed731b](https://github.com/avengers-p7/Documentation/assets/156056460/28443aa1-2efc-4ed6-8326-61aa058b4560)



