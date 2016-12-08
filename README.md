# RxAndroid with Retrofit

### Rx

* Rx stands for Reactive Extensions.
* Term Rx Created by Microsoft. 
* It is not a new language, It is just an other library say Retrofit, Glide etc.,

### Anatomy
1. Observable
2. Observer
3. Schedulers
4. Subscription

> * RxJava, at it’s core, is about two things: Observables and Observers.
* Observables are said to “emit” values.
* Their counterpart, Observers, watch Observables by “subscribing” to them.
* Observers can take actions when an Observable emits a value, when the Observable says an error has occurred, or when the * * * Observable says that it no longer has any values to emit. All three of these actions are encapsulated in the Observer * * * * interface. The corresponding functions are onNext(), onError(), and onCompleted().



```
                getIpApiObservable()                        --> Observable (Retrofit Call)
                .subscribeOn(Schedulers.io())              |--> Schdulers
                .observeOn(AndroidSchedulers.mainThread()) |
                .subscribe(new Subscriber<String>() {       --> Observer
                    @Override
                    public void onCompleted() {
                        Toast.makeText(MainActivity.this, "onCompleted", Toast.LENGTH_SHORT).show();
                    }

                    @Override
                    public void onError(Throwable e) {
                        Toast.makeText(MainActivity.this, e.getLocalizedMessage(), Toast.LENGTH_SHORT).show();
                    }

                    @Override
                    public void onNext(String s) {
                        tv_output.setText(s);
                    }
                });
```

### Refer :

[Vid By KG](https://www.youtube.com/watch?v=k3D0cWyNno4&t=925s)

[KG Vid Slides](https://speakerdeck.com/kaushikgopal/learning-rxjava-for-android-by-example)

[Android Authority](http://www.androidauthority.com/reactive-programming-with-rxandroid-711104/)

[medium - @kurtisnusbaum](https://medium.com/@kurtisnusbaum/rxandroid-basics-part-1-c0d5edcf6850#.55b1672l8)

[RxJava - Vogella](http://www.vogella.com/tutorials/RxJava/article.html)

[Blog-Danlew](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/)

---
>Glad to see you! Thank You.

