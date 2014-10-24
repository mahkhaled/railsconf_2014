## Service Extraction at Groupon Scale

#### Centralize Omnipotent Big-ass Rails Application

In 2009, after 8 months of release, 30k request per minute, everything was on fire.

They were not scaling properly.

Average commits was 500 commit/month, in a couple of years, average is 2000 commit/month.

They started thinking of using SOA.

They had alot of scaling problems. On of the biggest problems that prevented them from extracting services was model coupling.

Example:
* Order belongs to Deal and User.
* User has many Orders.
* Deal has many Orders. 

In the user's home page, it was required to display deal titles for that user.

* Code base was getting bigger, almost 2M LOC at this point.
* DB is on fire.
* Testing sucked
* 45 minutes for build to run
* Deploy process was terrible 3 hours

##### They decided to move to service extarction

They extracted the service to work on a nother database, but has a read access to the old database.

#### Inner-app service wall
* services directory contains extracted services.
* each service contains app, lib and spec directories (like a rails app).
* environment.rb iterated over the services and add them to the load path.


#### They built something called Route 66
To check, Is this end point used?
analyze logs to know which controllers/actions are being hit.

#### Facade as a service
Use Managers to hide complexity, as data could be retreived from different sources.

#### Messaging is critical

#### Avoid tangeled parts

#### Test at high level
when you start writing service extraction, you will write unit tests.

##### Communicate progress
When you solve a problem, share.

### Hassan' Notes
* The talk is very abstract. 
* They'r saying "You should think about X, You shoud think about Y"  without providing solutions.
* Silly advices, like "You need to write code good!!"
