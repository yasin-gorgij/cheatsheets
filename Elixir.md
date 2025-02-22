# Welcome to Elixir cheat sheet!

**Add language server directories to project .gitignore file**

`# Language server directories`

`/.elixir_ls/`

`/.elixir-tools/`

**Create a new project:**
`mix phx.new mahi --binary-id --install --no-gettext`

**Change generator setion of config.ex file to use binary_id and utc_datetime_usec:**
`
generators: [
    binary_id: true,
    timestamp_type: :utc_datetime_usec
  ]
`

**Create authentication in Phoenix project:**
`mix phx.gen.auth Accounts User users --live --binary-id --hashing-lib argon2`

**Add common dependencies**

`{:mix_unused, "~> 0.4", only: [:dev, :test], runtime: false},`
`{:mix_audit, "~> 2.1", only: [:dev, :test], runtime: false},`
`{:sobelow, "~> 0.13", only: [:dev, :test], runtime: false},`
`{:credo, "~> 1.7", only: [:dev, :test], runtime: false},`
**After installation you need to add `:unused` as a compiler to the list of Mix compilers in `project` function**

`compilers: [:unused] ++ Mix.compilers()`

**Then you just need to run `mix compile` or `mix compile --force` as usual and unused hints will be added to the end of the output.**

**Run `mix hex.audit` after adding a dependency or from time to time to check for retired hex package***

**Releasing a Phoenix Application**

`
mix phx.gen.secret
REALLY_LONG_SECRET
export SECRET_KEY_BASE=REALLY_LONG_SECRET
export DATABASE_URL=ecto://USER:PASS@HOST/database
`

`
mix deps.get --only prod && MIX_ENV=prod mix compile && MIX_ENV=prod mix assets.deploy && mix phx.gen.release && MIX_ENV=prod mix release
`
