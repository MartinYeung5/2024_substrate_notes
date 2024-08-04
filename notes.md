# Build application logic

The Build application logic tutorials focus on how you can customize the runtime using pallets, including how to add simple and complex pallets to the runtime and how to use pallets in combination with smart contracts.

## Build a local blockchain
1. open ubuntu
2. git clone https://github.com/substrate-developer-hub/substrate-node-template
3. cd substrate-node-template
4. cargo build --release
5. ./target/release/node-template --dev
6. go back window vscode
git clone https://github.com/substrate-developer-hub/substrate-front-end-template
7. yarn install
8. yarn start

## Add a pallet to the runtime
* https://docs.substrate.io/tutorials/build-application-logic/add-a-pallet/
clone 1 repo
* git clone https://github.com/substrate-developer-hub/substrate-node-template
* update runtime/Cargo.toml
add pallet-nicks under [dependencies]
* pallet-nicks = { version = "4.0.0-dev", default-features = false, git = "https://github.com/paritytech/polkadot-sdk.git", branch = "polkadot-v1.0.0" }
under [features]
in std, 
* "pallet-nicks/std",

run command:
* cargo check -p node-template-runtime --release

Error:
failed to load source for dependency of pallet-nicks

In this step, only review ( review the Config trait for the Balances pallet)
* Open the runtime/src/lib.rs file in a text editor.
Locate the Balances pallet and note that it consists of the following implementation (impl)code block:

you can see
"impl pallet_balances::Config for Runtime...."

* important point:
construct_runtime! (not in template, should add by own)
https://paritytech.github.io/polkadot-sdk/master/frame_support/macro.construct_runtime.html

* update runtime/src/lib.rs

## Create a new pallet
https://docs.substrate.io/tutorials/collectibles-workshop/03-create-pallet/

write pallet
https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/guides/your_first_pallet/index.html

write pallet
https://www.youtube.com/watch?v=ZPvSND1Mokc

1. go to substrate-node-template
2. cd pallets/template
3. delete benchmarking.rs, mock.rs, tests.rs
4. update lib.rs