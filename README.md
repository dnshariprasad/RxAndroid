# RxAndroid with Retrofit

> Includes..
* RxAndroid
* Retrofit

### More Words...

* Rx stands for Reactive Extensions.
* Term Rx Created by Microsoft. 
* It is not a new language, It is just an other library.

### Anatomy
1. Observable
2. Observer
3. Schedulers
4. Subscription

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

[Android Authority](http://www.androidauthority.com/reactive-programming-with-rxandroid-711104/)




