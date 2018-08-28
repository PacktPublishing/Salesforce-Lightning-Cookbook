Case 1:
<apex:page >
 <apex:slds />
<apex:form >
       <div class="slds-card" style="padding:2%">
         <apex:outputLabel value="Enter Account Name"></apex:outputLabel>
         <apex:inputText styleClass="slds-input"/>
         <apex:outputLabel value="Enter Contact Name"></apex:outputLabel>
         <apex:inputText styleClass="slds-input"/> <br/>  <br/>
         <div class="slds-button slds-button-group">
         <apex:commandButton styleClass="slds-button slds-button_success" value="Submit"/>
         <apex:commandButton styleClass="slds-button slds-button_brand" value="Search"/>
         <apex:commandButton styleClass="slds-button slds-button_destructive" value="Abort"/>
         </div>
      </div>
  </apex:form>
</apex:page>

Case 2 :  <apex:detail>
Case 3 : 
<apex:page standardController="Account">
 <!-- <apex:slds /> -->
  <apex:form >
    <apex:pageBlock title="Account Edit">
     <apex:pageBlockButtons >
      <apex:commandButton value="Submit" action="{!Save}"/>
      <apex:commandButton value="Cancel" action="{!Cancel}"/>
     </apex:pageBlockButtons>
     <apex:pageBlockSection title="Account Info">
      <apex:inputField value="{!Account.Name}"/>
      <apex:inputField value="{!Account.Type}"/>
      <apex:inputField value="{!Account.Rating}"/>
      <apex:inputField value="{!Account.Industry}"/>
      <apex:inputField value="{!Account.Phone}"/>
      <apex:inputField value="{!Account.WebSite}"/>
     </apex:pageBlockSection>
     <apex:pageBlockSection title="Billing Address">
      <apex:inputField value="{!Account.BillingStreet}"/>
      <apex:inputField value="{!Account.BillingCity}"/>
      <apex:inputField value="{!Account.BillingPostalCode}"/>
      <apex:inputField value="{!Account.BillingState}"/>
      <apex:inputField value="{!Account.BillingCountry}"/>
     </apex:pageBlockSection>
     
     <apex:pageBlockSection title="Shipping Address">
      <apex:inputField value="{!Account.ShippingStreet}"/>
      <apex:inputField value="{!Account.ShippingCity}"/>
      <apex:inputField value="{!Account.ShippingPostalCode}"/>
      <apex:inputField value="{!Account.ShippingState}"/>
      <apex:inputField value="{!Account.ShippingCountry}"/>
    </apex:pageBlockSection>
    </apex:pageBlock>
  </apex:form>
</apex:page>

Case 4 : 
<apex:page standardController="Account" recordSetVar="ShahAccounts">
 <apex:slds />
 <apex:form >
  <apex:pageBlock title="Records in Lightning Style" >
    <apex:pageBlockButtons >
      <apex:commandLink value="First" action="{!First}"/> | &nbsp;
      <apex:commandLink value="Previous" action="{!Previous}"/> | &nbsp;
      <apex:commandLink value="Next" action="{!Next}"/> |  &nbsp;
      <apex:commandLink value="Last" action="{!Last}"/> 
    </apex:pageBlockButtons>
          <apex:pageBlockTable value="{!ShahAccounts}" var="Acc">
             <apex:column value="{!Acc.Name}"/>
             <apex:column value="{!Acc.BillingState}"/>
             <apex:column value="{!Acc.Rating}"/>
             <apex:column value="{!Acc.Industry}"/>
             <apex:column value="{!Acc.WebSite}"/>
          </apex:pageBlockTable>
  </apex:pageBlock>
 </apex:form>
</apex:page>