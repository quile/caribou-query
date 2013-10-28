# caribou-query

This is just a set of very simple functions that simplify the
building of gather maps in a fashion that will be familiar to web
developers from other platforms.  It is a corollary to the
django/python/sqlalchemy query model of

    Thing.objects.filter(foo = "bar").sort(blah).all()

or the similar ActiveRecord querying model in RoR.

In Clojure, it looks like

    (-> (query :thing)
        (where :foo "bar")
        (where [:some :thing] "extra!")
        (order-by :foo :asc)
        (include :other)
        gather)

There is no magic; each successive method call simply adds in various
terms to the gather map and returns the new map.  The purpose of this is
to simplify code that does a lot of "assoc" and "merge" and "assoc-in" and
instead show a very clear query-building process.


## Usage

To create a gather map:

    (query)

or

    (query <model name>)

which simply return a map that can be threaded through the other functions and
then passed directly to gather.

TODO - document all functions


## License

Copyright © 2013 quile

Distributed under the Eclipse Public License, the same as Clojure.
