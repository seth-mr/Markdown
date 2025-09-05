

we are going to be talking abour *cron* ans more specifically how we can *interact with it* via *cronotabs*;
cronotabs is one of the procedd that is *started during boot*, wich is *responsible for facilitating and managing cron jobs* 

![](https://assets.tryhackme.com/additional/linux-fundamentals/part3/cron1.png)

A crontab is simply a *special file with formatting* that is recognised by *cron* procees to *execute line step-by-step* 
crontab require 6 values.

| Value | Description                               |
| ----- | ----------------------------------------- |
| MIN   | What minute to execute at                 |
| HOUR  | What hour to execute at                   |
| DOM   | What day of the month to execute at       |
| MON   | What month of the year to execute at      |
| DOW   | What day of the week to execute at        |
| CMD   | The actual command that will be executed. |

## ejemplo

Crontabs can be *edited by using crontab -e*, where you can select an editor (such as Nano) to edit your crontab.

Let's use the example of backing up files. You may wish to *backup "cmnatic"'s  "Documents" every 12 hours*. We would use the following formatting:

`0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/`

a feature of crontab was the *use of  *  if we want to provide a value for that specific field* 

![](https://assets.tryhackme.com/additional/linux-fundamentals/part3/cron3.png)
1