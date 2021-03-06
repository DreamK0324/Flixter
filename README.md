# Flix
Flix is an app that allows users to browse movies from the [The Movie Database API](http://docs.themoviedb.apiary.io/#).

## Flix Part 2

### User Stories

#### REQUIRED (10pts)

- [x] (8pts) Expose details of movie (ratings using RatingBar, popularity, and synopsis) in a separate activity.
- [x] (2pts) Allow video posts to be played in full-screen using the YouTubePlayerView.

#### BONUS

- [ ] Implement a shared element transition when user clicks into the details of a movie (1 point).
- [ ] Trailers for popular movies are played automatically when the movie is selected (1 point).
  - [ ] When clicking on a popular movie (i.e. a movie voted for more than 5 stars) the video should be played immediately.
  - [ ] Less popular videos rely on the detailed page should show an image preview that can initiate playing a YouTube video.
- [ ] Add a play icon overlay to popular movies to indicate that the movie can be played (1 point).
- [ ] Apply data binding for views to help remove boilerplate code. (1 point)
- [ ] Add a rounded corners for the images using the Glide transformations. (1 point)

### App Walkthough GIF

<img src="walkthrough.gif" width=550 title="Video Walkthrough" alt="Video Walkthrough" /><br>

### Notes

If you do not change the ID of the XML file, related events will blink back.

## Open-source libraries used
- [Android Async HTTP](https://github.com/codepath/CPAsyncHttpClient) - Simple asynchronous HTTP requests with JSON parsing
- [Glide](https://github.com/bumptech/glide) - Image loading and caching library for Android

---

## Flix Part 1

### User Stories

#### REQUIRED (10pts)
- [x] (10pts) User can view a list of movies (title, poster image, and overview) currently playing in theaters from the Movie Database API.

#### BONUS
- [x] (2pts) Views should be responsive for both landscape/portrait mode.
   - [x] (1pt) In portrait mode, the poster image, title, and movie overview is shown.
   - [x] (1pt) In landscape mode, the rotated alternate layout should use the backdrop image instead and show the title and movie overview to the right of it.

- [ ] (2pts) Display a nice default [placeholder graphic](https://guides.codepath.org/android/Displaying-Images-with-the-Glide-Library#advanced-usage) for each image during loading
- [x] (2pts) Improved the user interface by experimenting with styling and coloring.
- [ ] (2pts) For popular movies (i.e. a movie voted for more than 5 stars), the full backdrop image is displayed. Otherwise, a poster image, the movie title, and overview is listed. Use Heterogenous RecyclerViews and use different ViewHolder layout files for popular movies and less popular ones.

### Video Walkthough GIF

<img src="walkthrough.gif" width=550 title="Video Walkthrough" alt="Video Walkthrough" /><br>

### Notes
(1)
Cause of the problem: 
 java.lang.IllegalStateException:  Expected Android API level 21+ but was 19,

 newSslSocketFactory, 
 okhttp3.OkHttpClient,

To Solve this error, plz add the below lines in the build.gragle( App Module ) file
//-----------------

  implementation ("com.squareup.okhttp3:okhttp:3.12.12"){
      force = true //API 19 support
  }
  implementation 'com.squareup.okhttp3:logging-interceptor:3.12.12'

//-------------------
 
FATAL EXCEPTION : 
 java.lang.ExceptionInInitializerError 
 at okhttp3.OkHttpClient.newSslSocketFactory(OkHttpClient.java:263),
 at okhttp3.internal.platform.AndroidPlatform.buildIfSupported(AndroidPlatform.java:238),
 at okhttp3.internal.platform.Platform.findPlatform(Platform.java:202),
 at okhttp3.OkHttpClient$Builder.build(OkHttpClient.java:1015)

(2)
Shortcut key: Alt Insert >> Generate

### Open-source libraries used

- [Android Async HTTP](https://github.com/codepath/CPAsyncHttpClient) - Simple asynchronous HTTP requests with JSON parsing
- [Glide](https://github.com/bumptech/glide) - Image loading and caching library for Androids
