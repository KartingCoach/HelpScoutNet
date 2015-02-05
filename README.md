# HelpScoutNet
HelpScoutNet is a .NET class library that provides an easy-to-use interface for the helpscout.net web api

##Implemented

*Conversation
    *List Conversations
    *Get Conversations
    *Get Attachment Data
*Mailboxes
    *List Mailboxes
    *Get Mailbox
    *Get Folders
*Search
    *Conversations
    *Customers
*Tags
    *List Tags
*Users
    *List Users
    *Get User
    *List Users ny Mailbox
*Workflows
    *List Workflows

##Examples 

###Initialization of the client
```csharp
var client = new HelpScoutClient(ApiKey);
```
###Search customers
```csharp

var client = new HelpScoutClient(ApiKey);
var customersSearch = client.SearchCustomers(new SearchRequest{ Query = "(customer:\"johnappleseed@gmail.com\")"});
foreach (var searchresult in customersSearch.Items)
{
    Console.WriteLine(searchresult.FirstName + searchresult.LastName);   
}

```

###List Mailboxes
```csharp

var mailboxes = client.ListMailboxes();
foreach (var mailboxStub in mailboxes.Items)
{    
    Console.WriteLine(mailboxStub.Id);
}
  
```
