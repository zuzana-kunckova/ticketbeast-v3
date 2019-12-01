##Description of the errors

Followed instructions until adding the relevant columns to the database (Getting to Green: 07:08). From there on:

My error - `visit()` is an undefined method
Changed this to `get()`
New error - `see()` is an undefined method
Changed to `assertSee()`
Error: `assertSee()` is an undefined method

Googled around, tried to save `$this->get()` to a `$response` variable, called `assertSee()` on `$response`, no errors.

Added all required columns to the concerts migration table as indicated by the failing tests. When all columns were added:

- Adam’s error - A request to [http://localhost/concert/1] failed. Received status code [404]
- My error: InvalidArgumentException Failed asserting that 404 page contains The Red Chord

Added new Route and pointed it to `ConcertsController@show`.

- Adam’s error - ConcertsController does not exist
- My test passes.

Created ConcertsController. 

- Adam’s error - ‘show method does not exist’
- My error - InvalidArgumentException Failed asserting that 404 page contains The Red Chord.  

Added `show` method in the ConcertsController.

- Adam’s error - The current node list is empty
- My error - Failed asserting that ' ' contains "The Red Chord”.

Returned `concerts.show` view.

- Adam’s error - there is no `concerts.show` view
- My error - Failed asserting that ' ' contains "The Red Chord"

Created concerts folder and show.blade.php file

- Adam’s error - The current node list is empty
- My error - Failed asserting that ' ' contains "The Red Chord".

Added `<h1>{{ $concert->title }}</h1>` to show.blade.php

- Adam’s error: Undefined variable concert
- My error: InvalidArgumentException Failed asserting that 404 page contains The Red Chord  

In ConcertsController, passed the `$concert` variable to the view

- Adam’s error: Undefined variable concert in ConcertsController
- My test passes, even though VSCode underlines the `$concert` variable as it’s undefined

Defined `$concert = Concert::find($id);` in the ConcertsController

- Adam’s error: Failed asserting that the page contains ’with Lethargy and Animosity’
- My test passing

From now on, while adding all the other fields in the show.blade.php, Adam keeps getting errors to indicate which fields are still missing, while my test passes without having to add anything