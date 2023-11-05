# python-template


## Testing: PyTest

$ poetry run pytest --cov --cov-fail-under=100

## Wrapping Them Up in GitHook

Usually, I will use the pipeline to run all the commands above, but pipeline runs a bit slower than our local githook to ensure the commits are always right all the time.

run the installation for the pre-commit

$ poetry run pre-commit install

Now, you can try to run the pre-commit using

$ poetry run pre-commit run --all-files

and every time you commit, the pre-commit config will also runs.
You can always run:

git add .
git commit --no-verify -m "feat: ..."