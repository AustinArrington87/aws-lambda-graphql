# aws-lambda-graphql
App for querying subredits with Lambda, Node, GraphQL
APP WILL LET US : 
	•	Allow us to query Subreddits
	•	Return the fields we ask for. In this case, it will be  id, title, url, author, score, ups (upvotes), downs (downvotes) and content
	•	Allow us to specify a different Subreddit (default: javascript)
	
1)install node dependencies 

 $ npm init -y
 
2)include aws function handler

$ npm add —install aws-serverless-express
 
3) compress folder (compression issues from mac when going into AWS productionwhen compressing files on mac go into dir, highlight all directories / files and select "compress n" )
 
4) Creating Lambda Function in AWS 
 - Policy: Simple MicroService
 - Handler: change "index.handler" to "lambda.handler" 
 - Runtime: Node.js 6.10
 
 5) Setup API Gateway to make Lambda Function Available 
 	Integration Type: Lambda Function
	•	Use Lambda Proxy integration: Yes; check this field
	•	Lambda Region: Select the region in which you created the Lambda function (in my case, us-east-1)
	•	Lambda Function: Enter the function name
  
  5b) Add GET, POST Methods & Deploy 
 
 # Demo GraphQL App at https://stfqy47e55.execute-api.us-east-1.amazonaws.com/Production_1?query=%23%20Welcome%20to%20GraphiQL%0A%23%0A%23%20GraphiQL%20is%20an%20in-browser%20tool%20for%20writing%2C%20validating%2C%20and%0A%23%20testing%20GraphQL%20queries.%0A%23%0A%23%20Type%20queries%20into%20this%20side%20of%20the%20screen%2C%20and%20you%20will%20see%20intelligent%0A%23%20typeaheads%20aware%20of%20the%20current%20GraphQL%20type%20schema%20and%20live%20syntax%20and%0A%23%20validation%20errors%20highlighted%20within%20the%20text.%0A%23%0A%23%20GraphQL%20queries%20typically%20start%20with%20a%20%22%7B%22%20character.%20Lines%20that%20starts%0A%23%20with%20a%20%23%20are%20ignored.%0A%23%0A%23%20An%20example%20GraphQL%20query%20might%20look%20like%3A%0A%23%0A%23%20%20%20%20%20%7B%0A%23%20%20%20%20%20%20%20field(arg%3A%20%22value%22)%20%7B%0A%23%20%20%20%20%20%20%20%20%20subField%0A%23%20%20%20%20%20%20%20%7D%0A%23%20%20%20%20%20%7D%0A%23%0A%23%20Keyboard%20shortcuts%3A%0A%23%0A%23%20%20%20%20%20%20%20Run%20Query%3A%20%20Ctrl-Enter%20(or%20press%20the%20play%20button%20above)%0A%23%0A%23%20%20%20Auto%20Complete%3A%20%20Ctrl-Space%20(or%20just%20start%20typing)%0A%23%0A%7B%0A%20%20posts(subreddit%3A%22agriculture%22)%7B%0A%20%20%20%20title%0A%20%20%20%20author%0A%20%20%20%20url%0A%20%20%7D%0A%7D%0A  
 
 # post format 
 
 {
  posts(subreddit: "worldnews") {
    title
    author
    url
  }
}

