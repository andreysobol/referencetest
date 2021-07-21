# Result

```
non mutable var:
before change inside changejustvar - 0
after change inside changejustvar - 1
out of the function changejustvar - 0

mutable var:
before change inside changejustvar - 0
after change inside changejustvar - 1
out of the function changejustvar - 0

mutable var as mut reference:
before change inside changejustreference - 0
after change inside changejustreference - 1
out of the function changejustreference - 1

mutable reference as var:
before change inside changejustreference - 0
after change inside changejustreference - 1
out of the function changejustreference - 1
```

# Code copypaste

```
fn changejustvar(mut justvar: u8) {

    println!("before change inside changejustvar - {}", justvar);
    justvar = 1;
    println!("after change inside changejustvar - {}", justvar);

}

fn changejustreference(justreference: &mut u8) {

    println!("before change inside changejustreference - {}", justreference);
    *justreference = *justreference + 1;
    println!("after change inside changejustreference - {}", justreference);

}

fn main() {

    let justvar = 0;
    println!("non mutable var:");
    changejustvar(justvar);
    println!("out of the function changejustvar - {}", justvar);
    println!("");

    let mut justmutvar = 0;
    println!("mutable var:");
    changejustvar(justmutvar);
    println!("out of the function changejustvar - {}", justvar);
    println!("");

    println!("mutable var as mut reference:");
    changejustreference(&mut justmutvar);
    println!("out of the function changejustreference - {}", justmutvar);
    println!("");


    let justmutreference = &mut 0;
    println!("mutable reference as var:");
    changejustreference(justmutreference);
    println!("out of the function changejustreference - {}", justmutreference);

}
```