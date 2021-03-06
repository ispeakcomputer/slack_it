# Slack it! - Slack Alert Any Command Output 

I use this to report on anything I need to watch at the command line manually by instead firing with Cronjob and watching for output sent to Slack. 

Great for one off things that need to be watched or being proactive about something that will be monitored more in depth later.

#### Need A Few Examples? 

* Curl a api or website and parse out failure messages to alert on 
* Parse a specific error on a target machine to alert on

### Setup 
1. First setup a Slack webhook at Slack. 

2. Once the Slack webhook is setup test it using the script in this repo called **slack_test.sh** by running ```chmod +x slack_test.sh``` then ``` ./slack_test.sh TESTING!``` while inside the repo directory

3. Update the run_command function with the command you need to grab output from inside the **slack_it.sh** script. Its the only line in that function.

4. Make sure you use **grep** or **cut** to grab just the piece of output you need to send to Slack. Any output allowed will be the Slack alert

5. Update the **curl** command on line 19 with your proxy and add the correct Slack webhook. 

6. Fire with Cron to automate. 

![example kubernetes node slack alert](https://github.com/ispeakcomputer/slack_it/blob/master/readme_photo/photo.png?raw=true)


