<h3> Office Manager

<h5>The task was to model a network of typical office equipment:
<h5>• printer
<h5>• scanner
<h5>• coffee machine 
<h5>• copier
<h5>• vending machine
<h5>A simple monitoring/management tool which will be able to notify users of the status (online, offline or in error state) of each connected piece of equipment. All machines have unique alphanumeric codes.
 
 
<h5>I created the Class UML Diagram. Each machine processes a job in a different way.
 
 
 
 
![OfficeManager](https://github.com/IngaPosiunaite/QuizApplication/assets/119749457/f9305bb1-53aa-4206-b6b4-5f9493f11522)


 
 
 
<h5> Printer displays the description of their job in the console and then set the job field to null.
<h5> Scanner modifies their job to get it ready to be passed on to a printer. To that effect, scanner swaps the job’s owner with their machine code, replaces the first three letters in the job code with PRT and does not set the job to null afterwards. They do, however, have a method to allow clearing the job explicitly.
<h5> Coffee and vending machines check the job’s owner. If it starts with 1, the owner is senior management and gets coffee / food for free. Otherwise, the owner is notified via a message displayed in the console that a standard amount (10p) has been taken out of his/her account as payment for the job. The job is set to null afterwards.
<h5>Copier accepts jobs with extra data indicating the number of copies to make for that job. The copier prefix each copy it produces with the count of each copy along with the total number requested in that job. Finally, the copier sets the job field to null.

<h5>The manager is not a piece of office equipment. It is a fully digital system that monitors all machines in the office and has the main task of supervising the job assignment process. To this end, the manager will store a list of all the jobs currently active (that have not yet been processed) and a record of all available machines. 
<h5>The manager performs the following tasks:
<h5>• Assigns jobs. Every job in the list will be assigned to the first machine found that is capable of performing the job (the first three letters of the code match those of the job). If no compatible machine is found, the appropriate message is displayed in the console. 
<h5>• Processes jobs. Every machine in the system is asked to process the job previously assigned to it. If the machine is a scanner, the manager will explicitly retrieve the job processed by the scanner and assign it to the first printer available. At the end of the process, all jobs get deleted from the manager’s memory - even the ones that were not assigned to machines. 
