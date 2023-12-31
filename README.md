# Feed Case Study App
# Image Feed Feature Specs

# Story: Customer requests to see their image feed

Narrative #1
As an online customer:
I want the app to automatically load my latest image feed
So I can always enjoy the newest images of my friends

Sceanrios(Acceptance criteria)
Given the customer has connectivity
 When the customer request to see their feed
 Then the app should display the latest feed from remote
  And replace the cache with the new feed



Narrative #2
As an offline customer
I want the app to show the latest saved version of my image feed
So I can always enjoy images of my friends

Scenarios(Apcceptance criteria0
Given the customer doesn't have connectivity
 And there's a cached version of the feed
 And the cache is less than seven days old
When the customer requests to see the feed
Then the app should display the latest feed saved


Given the customer doesn't have connectivity
 And there's a cached version of the feed
 And the cache is seven days old or more
When the customer request to see the feed
Then the app should display an error message

Given the customer doesn't have connectivity
 And the cache is empty
When the customer request to see the feed
Then the app should display an error message


#  Use Cases

#  Load Feed From Remote Use Case

Data:
 URL

Primary course (happy path):

 1. Execute "Load Image Feed" command with above data.
 2. System downloads data from the URL
 3. System validates downloaded data.
 4. System creates image feed from valid data.
 5. System deiveers image feed



# Flow Chart

![feed_flowchart](https://github.com/algoives/feed-case-study/assets/99767772/ced53ec3-cbab-4f46-96b5-2d76ea14c1f8)


Feed Image

Property	Type
id	        UUID
description	String (optional)
location	String (optional)
url	        URL
Payload         contract

GET /feed 


200 RESPONSE

{

	"items": [
		{
			"id": "a UUID",
			"description": "a description",
			"location": "a location",
			"image": "https://a-image.url",
		},
		{
			"id": "another UUID",
			"description": "another description",
			"image": "https://another-image.url"
		},
		{
			"id": "even another UUID",
			"location": "even another location",
			"image": "https://even-another-image.url"
		},
		{
			"id": "yet another UUID",
			"image": "https://yet-another-image.url"
		}
		...
	]
 
}



