# diy-log

> Various console log level prefixes with support for color symbols and tags.

自定义控制台各种级别日志输出的前缀，支持颜色符号，标签和时间。


![img](./example/screenshot.png)



## Installation

```bash
npm install diy-log --save-dev
```



## Usage

```js
// for cjs
const logger = require('diy-log')
const { log, symbols, colors, tag } = logger


// for esm
import logger, {
  log,
  colors,
  symbols,
  tag
} from 'diy-log'
```

```js
time('time ...')

info('info ...')
done('done ...')
error('error ...')
warn('warn ...')

log(symbols.info, 'info ...')
log(symbols.done, 'done ...')
log(symbols.error, 'error ...')
log(symbols.warn, 'warn ...')


log(colors.dim('dim:text;'))
log(colors.blue('color: blue;'))
log(colors.bgGreen('bgcolor: green;'))
log(colors.bold('bold:text;'))
log(colors.italic('italic:text;'))
log(colors.underline('underline:text;'))


tag('info message')
tag('success message', 'done', 'success')
tag.warn('warning message')
tag.done('done message')
tag.info(colors.blue('info message'))
tag.error('error message')
```

## Methods

```ts
type Log = (...args: any[]) => void

type TagType = (message: string, label?: string) => void

interface Tag {
  (message: string, tag: 'info' | 'error' | 'done' | 'warn' = 'info', label?: string): void
  info: TagType
  error: TagType
  done: TagType
  warn: TagType
}
```

- `log`: Log;
- `time`: Log;
- `info`: Log;
- `error`: Log;
- `done`: Log;
- `warn`: Log;
- `tag`: Tag;
- `tag.info`: TagType;
- `tag.error`: TagType;
- `tag.done`: TagType;
- `tag.warn`: TagType;


## Thanks

[log-symbols](https://github.com/sindresorhus/log-symbols) , [picocolors](https://github.com/alexeyraspopov/picocolors) , [time-stamp](https://github.com/jonschlinkert/time-stamp)
