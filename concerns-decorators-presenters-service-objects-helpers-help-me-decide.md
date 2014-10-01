## Guidelines

* Methods < 5 lines
* Classes < 100 lines
* One instance variable in view

## Concerns

* Group by "domain"
* Use extend ActiveSupport::Concern And only included and module ClassMethods

## Drapper Decorator (delegator)

* Ex: Model file creating validation message with HTML tags Remove presentation code from model
* Why not use helpers?
* Because it may be related to the model and may be used in multiple controllers/views then helpers will be just functional code with messy OOP design
* Gem: https://github.com/drapergem/draper
* Decorators don't replace helpers but when helpers are not the best fit here

## Presenters

* Too many instances variables in controller
* Create a new class that take parameters in initializer
* Create separate method for each instance variable
* And Done!
* It will be also useulf for fragment caching by implementing instance method cache_key

## Business logic in Models

* Move logic from controllers to models and user services objects