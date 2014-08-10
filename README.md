# NAME

WebService::MerriamWebster - use Merriam-Webster dictionary API in Perl 

# SYNOPSIS

        use WebService::MerriamWebster;
        my $mw = WebService::MerriamWebster->new(dict => "collegiate", word => "$the-word-to-query", key => "$your-key-here");
        my $xml = $mw->raw_xml;  # a string
        my $dom = $mw->dom; # XML::LibXML::Document
        my @entries = $mw->entries(); # @entries is list of XML::LibXML::Element
        my $audio_uri = $mw->audio_url;  # ex. http://media.merriam-webster.com/soundc11/t/test0001.wav
        

# DESCRIPTION

WebService::MerriamWebster is an api to merriam-webster.com dictionary. It gives you xml result based on your query.
it use XML::LibXML to process the XML result (very basic). If you need to get the value of specific node, probably
you need to deal with the xml yourself.  

# Attributes

## dict

        has 'dict' => (
                is => 'rw',
                isa => 'Str',
                required => 1
        );

the dictionary you want to use

## word

        has 'word' => (
            is => 'rw',
            isa => 'Str',
            required => 1
        );

the word to query

## key

        has 'key' => (
            is => 'ro',
            isa => 'Str',
            required => 1
        );

## url 

the query url based on $dict, $word, $key

        reference: http://www.dictionaryapi.com/api/v1/references/$dic/xml/$word?key=$key

## raw\_xml

the xml you get based on your query

## dom

the dom (XML::LibXML::Document) base on your query  

# Method

## entries

the @entries of dom 

## audio\_url 

the audio url of the query word

# AUTHOR

Hao Wu <echowuhao@gmail.com>

# COPYRIGHT

Copyright 2013- Hao Wu

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO

[XML::LibXML](https://metacpan.org/pod/XML::LibXML)
