# zabbix-twilio-template

This is a twilio template to monitor twilio balance, and maybe other account information using Zabbix

On Server:
 * Import **template_twilio.xml** template
  
 * Create a new host for each twilio account you want to monitor

 * Theses hosts don't need a zabbix-agent, all requests will be made by the zabbix server (you can use 127.0.0.1 for then)

 * For each created host (twilio account) create the following **Macros**:
    * {$AUTH_TOKEN} -> you_twilio_account_auth_token
    * {$SID} -> your_twilio_account_sid

 * Add the imported template to your new hosts

# Items

The only item is your twilio current balance value. But let me know if you would like to monitor other things in your twilio account, since it would be pretty easy to add to this template.

I used this documentation to make this template: https://www.twilio.com/docs/usage/api/account 


# Triggers

There is a trigger for when the balance is below 5 dolars. This value can be changed globaly in the template Macro. But you can also change this for each account, in hosts Macro -> Inherited and host macros


