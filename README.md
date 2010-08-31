# flickr api reflected

A flickr client for node.js that uses the reflection api.

## Example

<pre>var options = {
    key: 'add_your_flickr_key',
    secret: 'add_your_flickr_secret',
    apis: ['contacts', 'photos'] // add the apis you'd like to use
};
flickr.connect(options, function(err, api) {
    if (err) throw err;

    api.contacts.getList(function(err, data) {
        if (err) throw err;

        sys.puts(sys.inspect(data.contacts.contact));
    });

    api.photos.search({tags: 'beach,iceland'}, function(err, data) {
        if (err) throw err;

        sys.puts(sys.inspect(data.photos.photo));
    });
});
</pre>

## Dependencies

If you need to use signed methods you have to install node with openssl.
