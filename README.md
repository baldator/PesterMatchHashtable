# PesterMatchHashtable
This module provides additional assertions for [Pester](https://github.com/pester/Pester) to help with testing hash table contents

## Installation

### PowerShell Gallery

You can install [PesterMatchHashtable](https://www.powershellgallery.com/packages/PesterMatchHashtable/) via the [PowerShell Gallery](https://www.powershellgallery.com/)

```powershell
Install-Module -Name PesterMatchHashtable
```

## Examples

MatchHashtable compares two hashtables.

```powershell
Describe "MatchHashtable examples" {
	It "single item hashtables match" {
       @{"a"=1} | Should MatchHashtable @{"a"=1}
    }
    It "hashtables  with the same contents match" {
        @{"a"=1;"b"="wibble"} | Should MatchHashtable @{"b"="wibble";"a"=1}
    }
    It "hashtables with different lengths do not match" {
        @{"a"=1} | Should Not MatchHashtable @{"b"="wibble";"a"=1}
    }
    It "hashtables with different lengths do not match" {
        @{"a"=1;"b"="wibble"} | Should Not MatchHashtable @{"b"="wibble"}
    }
    It "hashtables with different values do not match" {
        @{"a"=1;"b"="wibble"} | Should Not MatchHashtable @{"a"=123; "b"="wibble"}
    }
}
```

## Release Notes

### Version 0.0.1 11th July 2016
Pushed to PowerShell Gallery

Initial version of PesterMatchHashtable

## Future
* Wrap up to publish to chocolatey, psget