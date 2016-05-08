# asar

Package asar reads ASAR (Atom-Shell Archive) archives

    import (
        "os"

        "github.com/layeh/asar"
    )


    f, err := os.Open("sample.asar")
    if err != nil {
        panic(err)
    }
    defer f.Close()

    archive, err := asar.Decode(f)
    if err != nil {
        panic(err)
    }

    test := archive.Find("test", "file.txt")
    if test == nil {
        panic("file not found")
    }
    // print contents of test/file.txt in sample.asar
    fmt.Println(test.String())

## License

MPL 2.0

## Author

Tim Cooper (tim.cooper@layeh.com)