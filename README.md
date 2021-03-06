# storage.vim

## Usage

```markdown
$ vim s3://BUCKET/OBJECT
```

This executes `s3cmd get s3://BUCKET/OBJECT tempfile`, and shows the result as a new buffer.<br>
If you `:w[rite]`, then `s3cmd put tempfile s3://BUCKET/OBJECT` is executed.

```markdown
$ vim s3://BUCKET/OBJECT/
```

This executes `s3cmd ls s3://BUCKET/OBJECT/`, and shows the result as a quickfix window.

## Screenshot

![s3cmd](https://cloud.githubusercontent.com/assets/1040576/20217208/1544c4b2-a862-11e6-90c6-91d4c3629c0e.png)

## Requirement

The [s3cmd](https://github.com/s3tools/s3cmd) cli tool, or a same `get --force`
(overwrites the local file if it already exists), `put` and `ls` interfafce cli
tool.

## Option

If you have your favorite cli tool which provides the same interface as s3cmd, then you can add below line to your .vimrc.

```markdown
let g:storage_vim_cmd = 'command_name'
# default 'command_name' is 's3cmd'
```

## Installation

Use your favorite plugin manager, or

```markdown
# at terminal
$ git clone https://github.com/blp1526/storage.vim.git ~/.vim/bundle/storage.vim
```

```markdown
# at .vimrc
set runtimepath^=~/.vim/bundle/storage.vim
```

```markdown
# at Vim
:helptags ~/.vim/bundle/storage.vim/doc
```

## Development

This repository's
[spec](https://github.com/blp1526/storage.vim/tree/master/spec) directory has
test code. If you want to run test code, open spec file with
`vim --clean spec/storage_spec.vim`, and exec `source %`.

## Contributing

1. Fork it ( https://github.com/blp1526/storage.vim/fork )
1. Create your feature branch (`git checkout -b my-new-feature`)
1. Commit your changes (`git commit -am 'Add some feature'`)
1. Push to the branch (`git push origin my-new-feature`)
1. Create a new Pull Request
