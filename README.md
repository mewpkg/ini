## ini

This package reads and writes run of the mill ini configuration files.
It has one additional feature: The ability to write multiple values for
the same key by using the `<` operator, as opposed to `=`:

	[keys]
	auth < sd8f0h2n239iu2
	auth < 908y23ncpds98y
	auth < 9(*Skl23;8f)-s

This yields a slice of string values:

	keys := file.Section("keys")
	
	keys["auth"] == []string {
		"sd8f0h2n239iu2",
		"908y23ncpds98y",
		"9(*Skl23;8f)-s",
	}

We can use this to conveniently supply rotating encryption keys without
having our code worry about changing ini key names.


### Usage

    go get github.com/jteeuwen/ini

Refer to the package documentation for usage examples.


### License

Unless otherwise stated, all of the work in this project is subject to a
1-clause BSD license. Its contents can be found in the enclosed LICENSE file.

