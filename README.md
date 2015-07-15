# ltsv2csv

Convert LTSV (Labeled Tab Separated Values) to CSV (or TSV)

## Installation

```
    $ gem install ltsv2csv
```

## Usage

`ltsv2csv` is a command line tool. It converts stdin LTSV lines to stdout CSV(TSV). The first row of output become a header row.

### Example 1

```
$ cat input.ltsv
foo:111   bar:222   baz:333
foo:444   bar:555   baz:666
foo:777   bar:888   baz:999

$ cat input.ltsv | ltsv2csv 
bar     baz     foo
222     333     111
555     666     444
888     999     777
```

### Example 2

Filter columns to output by `-k` option. Multiple keys can be specified with , separator. The specified key order is reflected in column order of csv output.

```
$ cat input.ltsv | ltsv2csv  -k baz,bar
baz     bar
333     222
666     555
999     888
```

### Example 3

Default column separator is TAB. By `-c` option, it can be changed.

```
$ cat input.ltsv | ltsv2csv -k baz,bar -c ,
baz,bar
333,222
666,555
999,888
```



## Contributing

1. Fork it ( https://github.com/[my-github-username]/ltsv2csv/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
