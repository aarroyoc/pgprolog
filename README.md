# Prolog language for PostgreSQL

This is a PostgreSQL extension that allows writing stored procedures in Prolog.

This embeds [Scryer Prolog](https://www.scryer.pl) into a PostgreSQL extension.

**Proof of concept!** Not ready for any actual use.


## Running

Run with `cargo pgrx run`.

Then you can create the extension and language:
```
CREATE EXTENSION pgprolog;
CREATE LANGUAGE plprolog HANDLER plprolog_call_handler;
CREATE FUNCTION myfunc(a TEXT) RETURNS TEXT AS 'parent(alice,bob). handle(In,Out) :- parent(In,Out).' LANGUAGE plprolog;
SELECT myfunc('alice');
```
