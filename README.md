#usage
this file based otp_src/lib/tools/src/make.erl, support the multiple processes compile.

in your Makefile or script :
`erl -eval "case make:files([\"mmake.erl\"], [{outdir, \"ebin\"}]) of error -> halt(1); _ -> ok end" \
    -eval "case mmake:all(8,[$(MAKE_OPTS)]) of up_to_date -> halt(0); error -> halt(1) end."`

