# IBM Full Stack Certificate Containers and MicroServices Final Project

## Technology used:

* Backend: RESTAPI, Docker(Create Dockerfile), Kubernete, OpenShift
* Frontend: HTML, CSS, JavaScript

## Scenario
* Business Profile: CheckNBuy, a products comparison Company, allows customers to find the dealers for products they want to buy on their website.  Customers can find the rates offered by the dealers for each of these rpducts and compare them to get an idea of competitive pricing.  CheckNBuy currently have two repositories (Node.js application and Python application).
* Task:
* 1. Deploy these applications on Code engine and obtain URL access to the API endpoints
  2. Clone anotherr repository which will use these API endpoints and deploy the front-end application through the deployment URL
 
 ## Environment Setup on IBM Cloud IDE Theia

 * Set up Code Engine

 1. Open the Code Engine CLI
 2. Deploy the Product Detail python application which provides API endpoints that can be used to get product details

 $ ibmcloud ce application create --name prodlist --image us.icr.io/${SN_ICR_NAMESPACE}/prodlist --registry-secret icr-secret --port 5000 --build-context-dir products_list --build-source <https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git>

 3. Deploy the Dealer Pricing Details Node.js application, which provides API endpoints that can be used to get the dealer pricing details
 $ ibmcloud ce application create --name dealerdetails --image us.icr.io/${SN_ICR_NAMESPACE}/dealerdetails --registry-secret icr-secret --port 8080 --build-context-dir dealer_details --build-source <https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git>

## Modify and Deploy Frontend application
* Update the index.html file with deployed URL for product and dealer details

* deploy the frontend application by pointing the build-source to the current directory

* Click the link to load homepage