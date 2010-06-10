.. -*- restructuredtext -*-

django-twitter-tags is an app to easily load twitter messages using template tags

Installation
============

Download ``django-twitter-tags`` and put it on your python path.

Configuration
=============

Add this to your list of ``INSTALLED_APPS`` in ``settings.py``::

    INSTALLED_APPS = (
        'django.contrib.admin',
        'django.contrib.auth',
        ... 
        'django_twitter_tags',
        ...
    )

Sample Usage
============

The tag takes three arguments which are ``user``, ``number_of_tweets``, and ``alias``. Usage is straight forward and is best explained using an example::
    {% load twitter_tags %}
    {% get_twitter_messages user MarkWLiu limit 5 as tweets %}
    <ul>
    {% for tweet in tweets %}
        <li>
            <a href="{{ tweet.url }}">({{ tweet.time }}) {{ tweet.text }}</a>
        </li>
    {% endfor %}
    </ul>

In this example, the user is MarkWLiu and it received 5 tweets, which are now in a list in the variable ``tweets``. Each tweet also has three fields, ``url``, ``time``, and ``text``.

Good luck!
