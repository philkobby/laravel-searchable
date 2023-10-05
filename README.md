# laravel Searchable
A simple package to add search functionality to Laravel models.

Installation :

```
composer require Kobbex/laravel-searchable
```
Usage :
- use ```Searchable``` trait in your model
- Define ```$searchable``` property in your model to select which columns to search in

Example (User Model Relation With Post): 

```
use Kobbex\Searchable\Searchable;

class User extends Model {

  use Searchable ;
  protected $searchable = ['name', 'mobile', 'posts.title','posts.comments.title'];
  
  public function posts(){
    return $this->hasMany(Post::class);
  }
  ```
  
  Example (Post Model Relation with Comment):
  
  ```
  class Post extends Model {
  
  public function comments(){
    return $this->hasMany(Comment::class);
  }
  ```
