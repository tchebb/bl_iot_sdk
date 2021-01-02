.PHONY: app clean

DIRECTORIES := $(wildcard */)

app: $(DIRECTORIES)

$(DIRECTORIES)::
	echo building $@...
	# Use "+" to tell Make that this line's purpose is to invoke a submake,
	# since that's all that genromap does. This ensures it doesn't count
	# against the number of parallel jobs we're allowed.
	+cd $@ && ./genromap

clean:
	find . -name build_out | xargs rm -rf
