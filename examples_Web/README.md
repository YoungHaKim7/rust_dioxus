# Source

https://docs.rs/dioxus-web/latest/dioxus_web/fn.launch.html

https://dioxuslabs.com/

https://dioxuslabs.com/docs/0.3/guide/en/

# Tooling

To develop your Dioxus app for the web, you'll need a tool to build and serve your assets. We recommend using dioxus-cli which includes a build system, Wasm optimization, a dev server, and support hot reloading:

```
cargo install dioxus-cli
```

Make sure the `wasm32-unknown-unknown` target for rust is installed:

```
rustup target add wasm32-unknown-unknown
```

# Creating a Project

Create a new crate:

```
cargo new --bin demo
cd demo
```

Add Dioxus and the web renderer as dependencies (this will edit your Cargo.toml):

```
cargo add dioxus
cargo add dioxus-web
```

Edit your main.rs:

```
#![allow(non_snake_case)]
// import the prelude to get access to the `rsx!` macro and the `Scope` and `Element` types
use dioxus::prelude::*;

fn main() {
    // launch the web app
    dioxus_web::launch(App);
}

// create a component that renders a div with the text "Hello, world!"
fn App(cx: Scope) -> Element {
    cx.render(rsx! {
        div {
            "Hello, world!"
        }
    })
}
```

And to serve our app:

```
dioxus serve
```
