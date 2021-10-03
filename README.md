# Design Description


* At starting, user is presented with the main menu, allowing user to:
  1. enter or edit current job details, 
  1. enter job offers when current job is null, 
  1. adjust the comparison settings, or 
  1. compare job offers (disabled if no job offers were entered yet).
  To realize this requirement, we added a UserMainMenu class as an entry class which can allow the user to do all the operations listed above.
 
 
* There are 6 buttons which stand for 4 methods in Driver class. 
  1. "updateJob" is to enter/edit current job.
  1. "createJob" is to enter new job. 
  1. “changeSettings” is to adjust the comparison settings. 
  1. “compareJobs” is to compare job offers.
  1. "rank" is to rank job offers.
  1. "save" is to submit changes.
  
  
* When choosing to enter current job details, “updateJob” operation in UserMainMenu class is executed. 
Inside this operation, we will get current job from "jobCurrent" attribute. 
If the value is null, createJob() from UserMainMenu class is called to create a current job. A new Job object will be created. 
Otherwise, updateJob() inside UserMainMenu class is called to edit the details of the Job object upon clicking save.
We will calculate job score upon clicking save button and save the score to jobScore attribute of Job.
We did not address the navigation requirements in the diagram as they will be represented as part of the GUI.
  
  
* When choosing to enter job offers, “createOffer” operation in Driver class is executed. 
Inside this operation, createJob() from UserMainMenu class is called to create a new job offer. 
Once the user clicks save, a new job will be created and save to job list.
We will calculate job score upon clicking save button and save the score to jobScore attribute of Job.
We did not address the navigation requirements in the diagram as they will be represented as part of the GUI.

  
* When the user clicks compare the offer with the current job details, compareJob(Job j1, Job j2) from UserMainMenu class is called to compare the jobs.
This functionality will be enabled if there are either (1) at least two job offers, in case there is no current job, or (2) at least one job offer, in case there is a current job.
  
   
* When adjusting the comparison settings, “changeSettings” operation in UserMainMenu class is executed. 
We added a ComparisonSetting class with all the attributes listed above. 
We assigned a default value of 1 to all the integer weights to begin with so that all the factors are considered equal when no weights are assigned.
When settings are changed, all job scores will be recalcualted and saved to jobScore attribute of each job.
  
  
* When ranking jobs, the job scores of each job will be ranked accordingly and returned.
  
  
