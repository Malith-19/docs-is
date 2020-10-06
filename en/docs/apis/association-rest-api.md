---
template: templates/swagger.html
---

# User Account Associations API Definition - v1

!!! Note
    Follow the instructions given below to try out the REST APIs with your local instance of WSO2 Identity Server. 
    
       1.  Click on **Authorize** and provide the desired values for authentication. 
       2.  Expand the relevant API operation and click **Try It Out**.  
       3.  Fill in relevant sample values for the input parameters and click **Execute**. 
            You will receive a sample curl command with the sample values you filled in. 
       4.  Add a `-k` header to the curl command and run the curl command on the terminal with a running instance of WSO2
         IS. 
         
    **Before trying out the embedded postman collection with the "Run in Postman" option, make sure the following conditions are satisfied.**
    
       1. Create a user named `john`, with the password `pass123` in the tenant `carbon.super`.
       2. The id value for the local user association `john` is used for some API calls, which is assumed as 
       `UFJJTUFSWS9qb2hu`(This value is returned when a GET request is made to `/me/associations`(or 
       `/{user-id}/association`) API, once the association between `john` and `admin` users are created with the POST 
       request to the `/me/associations` API).
       3. Create an IdP with the name `ExternalIdP` in the tenant `carbon.super`.
       4. Create a federated association with a user in the above IdP for the `admin` user. The id of this 
       association(which is equal to `2e053351-0d69-476e-81df-04a9cfdfb50e` in the provided postman samples) is used 
       for some API calls. This id can be retrieved by making a GET request to the `/me/federated-association`(or 
       `/{user-id}/federated-association`) API.
     
<div id="swagger-ui"></div>
<script>
window.onload = function() {
  // Begin Swagger UI call region
  const ui = SwaggerUIBundle({
    url: ".../../apis/restapis/association.yaml",
    dom_id: '#swagger-ui',
    deepLinking: true,
    validatorUrl: null,
    presets: [
      SwaggerUIBundle.presets.apis,
      SwaggerUIStandalonePreset
    ],
    plugins: [
      SwaggerUIBundle.plugins.DownloadUrl
    ],
    layout: "StandaloneLayout"
  })
  // End Swagger UI call region

  window.ui = ui
}
</script>

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/ecd26c008975ebf4eafa)