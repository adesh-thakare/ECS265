# ECS 265 Final Project 
Crowdfunding using Scrypto Radix Blockchain

Go into the scrypto directory: cd scrypto
Reset the simulator: resim reset
Create the manager account: resim new-account -> Store the account address and private key somewhere
Create the member account: resim new-account -> Store the account address and private key somewhere
Build and deploy the blueprint: resim publish .
Instantiate a Campaign component: resim call-function [package_address] Campaign create_campaign 10 -> Store the component address and the second resource address (member badge address)
Switch to the second account: resim set-default-account [account2_address] [account2_priv_key]
Contribute 11 XRD to become a member: resim call-method [component_address] contribute 11,resource_sim1qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqzqu57yag
Create a request to send 10 XRD to the manager: resim call-method [component_address] create_request "hello" 10 [account1_address] 1,[member_badge_address]
Switch back to the first account: resim set-default-account [account1_address] [account1_priv_key]
Approve the request: resim call-method [component_address] approve_request 0 1,[member_badge_address]
Finalize the request: resim call-method [component_address] finalize_request 0 1,[member_badge_address]
Look at the resource in account1: resim show [account1_address]. It should show 1010 XRD!
