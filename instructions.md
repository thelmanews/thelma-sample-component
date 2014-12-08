1.  Creating an Element
    
    a. Include the HTML import for Polymer
    b. Create the tag for the Polymer element and name it
       - All element names have to have a "-" in it
       - Thelma components begin with the prefix "th-"     

2.  Determine which attributes the component should have and publish them
    a. Elements can have any number of attributes that can be published. When you publish an attribute, it means that you can pass values for that attribute inline. To publish attributes, simply define attributes="" in the component definition.
    b. These attributes can be used in the template as variables, using {{}} notation, and they have two way data binding. When the values change, the template will automatically reflect changes. 

3.  Elements can have JavaScript and styles associated with them too. These are encapsulated in the Shadow DOM and only impact the component itself, nothing outside of it. 
    a. Styles can be defined in a separate stylesheet or within the component itself using <style></style> tags
    b. JavaScript for the component is wrapped in a Polymer object, like this:
      <script>
        Polymer({
          // JS code for element goes here
        });
      </script>
    c. Make sure to remove the 'noscript' attribute from the element definition

4.  All custom functions and attributes default values are defined as object properties. 
    a. Example:
        Polymer({
          firstName: "foo",
          lastName: "bar",
          ready: function(){
            this.sayMyName();
          },
          sayMyName: function(){
            console.log(this.firstName + " " + this.lastName);
          }
        });
    b. If a value for an attribute is defined in the HTML, it will override the default
       Example: <th-sample-component lastName="thelma"></th-sample-component>  
                // "foo thelma" will be printed to the console

5.  Extending from another component.
    a. An element can extend from another element, in which case it will inherit all attributes and custom methods of that parent element. 
    b. To do this, just specify the name of the parent element in the definition and include the import at the top of the element file.
      Example: 
        <polymer-element  name="th-sample-component" extends="th-animated">
        
    c. Thelma components extend either from: 
       - 'th-animated' => if the component has animation, or
       - 'th-d3-chart' => if the component will utilize the d3 library 



  

