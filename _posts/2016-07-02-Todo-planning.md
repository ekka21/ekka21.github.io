---
title: Todo planning
date: 2016-07-2
author: ek
layout: post
---
It's time to build a prototype. Here are my thought that comes into my
mind right now.
- I'm building a todo app.
- Ok, I need a user story.
- An user goes to this website and can:
- create a todo item
- delete a todo item
- mark a todo item as completed
- view todo items
- share a todo link with a unique url that gets created automatically
- Let's bootstrap up all of these functionality up with
[Laravel](http://laravel.com)
- Try to minimize the frontend work as much as possible.

That should be good enough. Let's do this.


#Building an app

## create a database schema
- `php artisan make:migration create_template_table`
and also `php artisan make:migration create_todo_table`

```
```

## create database seeder so we have some dummy data to work with.
- `php artisan make:seeder TodoTableSeeder`
```
public function run()
{
  App\Template::truncate();
  App\Todo::truncate();
  foreach(range(0,5) as $i)
  {
    App\Template::insert([
      'name' => str_random(10),
    ]);
  }

  $templates = App\Template::all();
  $faker = Faker::create();

  foreach($templates as $template)
  {
    foreach(range(0,5) as $i)
    {
      App\Todo::create(['title' => $faker->sentence, 'template_id' => $template->id]);
    }
  }
}
```


