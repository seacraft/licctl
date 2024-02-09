# Copyright license tools
![workflow ci](https://github.com/seacraft/licctl/actions/workflows/ci.yml/badge.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/seacraft/licctl?)](https://goreportcard.com/report/github.com/seacraft/licctl)
[![golangci badge](https://github.com/golangci/golangci-web/blob/master/src/assets/images/badge_a_plus_flat.svg)](https://golangci.com/r/github.com/seacraft/licctl)
[![release](https://img.shields.io/github/release-pre/seacraft/licctl.svg)](https://github.com/seacraft/licctl/releases)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/mum4k/termdash/blob/main/LICENSE)
[![Releases](https://img.shields.io/github/downloads/seacraft/licctl/total.svg)](https://github.com/seacraft/licctl/releases)


> English | [中文](README_zh.md)

## Install

```bash
$ go install github.com/seacraft/licctl
```

Help information

```bash
$ licctl -h
Usage: licctl [flags] pattern [pattern ...]

The program ensures source code files have copyright license headers
by scanning directory patterns recursively.

It modifies all source files in place and avoids adding a license header
to any file that already has one.

The pattern argument can be provided multiple times, and may also refer
to single files.

Flags:

      --check                check only mode: verify presence of license headers and exit with non-zero code if missing
  -h, --help                 show this help message
  -c, --holder string        copyright holder (default "Google LLC")
  -l, --license string       license type: apache, bsd, mit, mpl (default "apache")
  -f, --licensef string      custom license file (no default)
      --skip-dirs strings    regexps of directories to skip
      --skip-files strings   regexps of files to skip
  -v, --verbose              verbose mode: print the name of the files that are modified
  -y, --year string          copyright year(s) (default "2021")
```

Parameter Description：

- `--check` Check only
- `-f, --licensef` Specify copyright header file
- `-v` Print changed files
- `--skip-dirs` Skip specified folder

## Getting Started

1. Create copyright header file

```bash
$ cat ./boilerplate.txt
 Copyright 2024 The seacraft Authors

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

 http:www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
```

2. Check whether the file contains the copyright header

```bash
$ licctl --check -f ./boilerplate.txt . --skip-dirs=third_party
```

3. Add copyright header to files missing copyright header

```bash
$ licctl -v -f ./boilerplate.txt . --skip-dirs=third_party
```
## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=seacraft/licctl&type=Date)](https://star-history.com/#seacraft/licctl)