#usage
this file based on otp_src/lib/tools/src/make.erl, support the multiple processes compile.

the exported functions are like make.erl, except for add the Worker Number as the first 
argument for every functions.

e.g. mmake:all(5), means you compile the codes defined in Emakefile by 5 workers.

in your Makefile or script :

`erl -eval "case make:files([\"mmake.erl\"], [{outdir, \"ebin\"}]) of error -> halt(1); _ -> ok end" 
    -eval "case mmake:all(8,[$(MAKE_OPTS)]) of up_to_date -> halt(0); error -> halt(1) end."`

