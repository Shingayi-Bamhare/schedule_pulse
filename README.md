This module exposes functionality to create receivers that
receive notifications after a specified period of time or at
a specified frequency.

# Examples

At its simplest, oneshot_ms can be used to put the thread to
sleep. Unlike with std::thread::sleep, this could be used with
Select to be waiting for one of several Receivers to fire.

    use timer::oneshot_ms;

    let timer = oneshot_ms(1500);
    timer.recv().unwrap();
    println!("1.5 seconds have elapsed.");

Periodic Receivers can be created using periodic_ms.

    loop {
        tick.recv().unwrap();
        println!("Tick");
        tock.recv().unwrap();
        println!("Tock");
    }