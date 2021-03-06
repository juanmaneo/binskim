BinSkim Binary Analyzer
=======================

This repository contains source code for BinSkim, a portable executable scanner that validates compiler/linker settings and other security-relevant binary characteristics.
 
Getting Started as a Developer
==============================

1. Clone the repository
2. Load and compile src\BinSkim.sln

Execute output in bld\bin\BinSkim.Driver for testing.

Submitting Pull Requests
========================
Run test.cmd at the root of the enlistment to ensure that all tests pass, and x64 and x86 release builds succeed.

Getting Started as a User
=========================
Expand x64 or x86 version of tool from latest release

*Latest stable Github x64 version:* [1.2.4-beta x64](https://github.com/Microsoft/binskim/releases/download/v1.2.4-beta/binskim.1.2.4-beta.x64.zip)

*Latest stable Github x86 version:* [1.2.4-beta x86](https://github.com/michaelcfanning/binskim/releases/download/v1.2.4-beta/binskim.1.2.4-beta.x86.zip)

Download from Nuget

*Latest stable Nuget version:* [1.2.4-beta](https://www.nuget.org/packages/BinSkim/)

Command-Line Documentation
==========================
  -o, --output        File path to which analysis output will be written.

  -v, --verbose       Emit verbose output. The resulting comprehensive report
                      is designed to provide appropriate evidence for
                      compliance scenarios.

  -r, --recurse       Recurse into subdirectories when evaluating file
                      specifier arguments.

  -p, --policy        Path to policy file that will be used to configure
                      analysis. Pass value of 'default' to use built-in
                      settings.

  -s, --statistics    Generate timing and other statistics for analysis
                      session.

  -h, --hashes        Output SHA-256 hash of analysis targets when emitting
                      SARIF reports.

  --sympath           Symbols path value, e.g.,
                      SRV*http://msdl.microsoft.com/download/symbols or
                      Cache*d:\symbols;Srv**http://symweb

  --help              Display this help screen.

  --version           Display version information.

  value pos. 0        One or more specifiers to a file, directory, or filter
                      pattern that resolves to one or more binaries to analyze.

Example Command-Line
====================
binskim.exe c:\bld\*.dll --recurse --policy default --output MyRun.sarif

See the [SARIF](https://github.com/sarif-standard/sarif-spec/) site for more information on the 'Static Analysis Results Interchange Format'
