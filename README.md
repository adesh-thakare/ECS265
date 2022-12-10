# ECS 265 Final Project 
Crowdfunding using Scrypto [Radix](https://www.radixdlt.com/) Blockchain

## How to test
1. Go into the scrypto directory: `cd scrypto`
1. Reset the simulator: `resim reset`
1. Create the manager account: `resim new-account` -> Store the account address and private key somewhere
1. Create the member account: `resim new-account` -> Store the account address and private key somewhere
1. Build and deploy the blueprint: `resim publish .`
1. Instantiate a Campaign component: `resim call-function [package_address] Campaign create_campaign 10` -> Store the component address and the second resource address (member badge address)
1. Switch to the second account: `resim set-default-account [account2_address] [account2_priv_key]`
1. Contribute 11 XRD to become a member: `resim call-method [component_address] contribute 11,resource_sim1qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqzqu57yag`
1. Create a request to send 10 XRD to the manager: `resim call-method [component_address] create_request "hello" 10 [account1_address] 1,[member_badge_address]`
1. Switch back to the first account: `resim set-default-account [account1_address] [account1_priv_key]`
1. Approve the request: `resim call-method [component_address] approve_request 0 1,[member_badge_address]`
1. Finalize the request: `resim call-method [component_address] finalize_request 0 1,[member_badge_address]`
1. Look at the resource in account1: `resim show [account1_address]`. It should show 1010 XRD!

## UI diagrams
#### Main Page:
![image](https://user-images.githubusercontent.com/44316648/206825085-b5776df0-88b0-4130-b22e-e28f48d130a3.png)
#### Create Campaign
![image](https://user-images.githubusercontent.com/44316648/206825240-fba05f0c-02e3-444e-b2d5-c397ffb7e385.png)
#### Open Campaign:
![image](https://user-images.githubusercontent.com/44316648/206825145-6130eed0-8e39-4786-a7b5-b5f135e33607.png)
![image](https://user-images.githubusercontent.com/44316648/206825221-adf5b4f2-dac2-4cac-b341-1cda72fc7b7b.png)
#### Campaign Show:
![image](https://user-images.githubusercontent.com/44316648/206825181-665f095e-b9d9-457a-8ed8-31bfb246b4c0.png)
![image](https://user-images.githubusercontent.com/44316648/206825182-b7b5ecd2-a3ba-4f91-a4ae-65d86237908a.png)
#### Create Requets
![image](https://user-images.githubusercontent.com/44316648/206825301-2a677b46-8f28-43f1-8018-3547609b05dd.png)
#### View Requests
![image](https://user-images.githubusercontent.com/44316648/206825264-cd7affaa-7c9b-41dd-949e-3c070a5478f0.png)


## Demo and PPT
- Our demo can be [found here](https://drive.google.com/file/d/1SGYJ1ws0Q5VSNzR4CAFb5RQMHy46QYBU/view?usp=sharing)
- The presentation can be [found here](https://docs.google.com/presentation/d/1wZ35bw-Ks85Uil0jOMCuLJeRm51LV1xn6hsDynkHWps/edit#slide=id.p)
