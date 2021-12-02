## Lab 4 Topic Review

In this week's lab we will mostly focus on polishing our apps. This includes adding animation and further styling.

### Glossary of concepts introduced
Below is a list of concepts / terms that we will encounter in this week's lab, along with a short description and links for further reading if you're interested in learning more.

#### View Properties  / Property Animators

Every view has certain 'properties' that can change and be animated. For example, one property that all views have is 'alpha'. The alpha property represents the transparency of a view. If a view's alpha = 0, the view would be completely invisible. If a view's alpha = 0.5, it would be half transparent. With property animators, we can animate a view changes it's transparency.

[Quick summary of the different property animations](https://guides.codepath.org/android/animations#property-animations)  
[Read about all the other types of properties that you can set and animate on views](https://developer.android.com/guide/topics/graphics/prop-animation#views)

#### AnimationListener
Often times when we want to execute an animation we also want to do some 'setup' before the animation plays and 'cleanup' after the animation completes. `AnimationListener` gives us callbacks for knowing when an animation starts / ends, so we can hide and show the appropriate views when necessary. For example, if we wanted to animate a view disappearing, after the animation finishes we would need to set the visibility of the view to `INVISIBLE`, and this can be more easily done with an `AnimationListener`

[Specific example using an AnimationListener](https://guides.codepath.org/android/animations#1-using-xml)  

#### Activity Transitions

In addition to property animations for views, we can also manage the animations and transitions for Activities as they become visible on screen. We do this by managing the transitions around the time we trigger an intent. The basic approach is that right after executing an intent with startActivity, you call the overridePendingTransition method and provide it with the animations you want played.

[Implementing Activity Transitions](https://guides.codepath.org/android/Animations#activity-transitions)
