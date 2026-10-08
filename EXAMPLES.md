# Before / After

Anchor the model on these. The facts stay the same. Only the language changes.

## Example 1 — a deploy step

**Before**
> In order to deploy the service, you'll first want to make sure that all of the
> environment variables have been properly configured, and then you can go ahead
> and trigger a new build, which should subsequently pick up the latest changes.

**After (STE)**
> Deploy the service:
> 1. Make sure you set all the environment variables.
> 2. Start a new build.
> 3. The build uses the latest changes.

## Example 2 — a description

**Before**
> This function is basically responsible for handling the various edge cases that
> can potentially arise when the input data happens to be malformed or incomplete.

**After (STE)**
> This function handles bad input. It checks for malformed data. It checks for
> incomplete data.

## Example 3 — a warning

**Before**
> Note that you should probably back up the database before running this, since
> the migration is destructive and could result in data loss if something fails.

**After (STE)**
> WARNING: This migration removes data. A failure can cause data loss.
>
> Make a backup of the database before you start the migration.

## Example 4 — an API how-to

**Before**
> To utilize the endpoint, simply pass your API key via the Authorization header,
> and the response will subsequently contain a JSON object with the results.

**After (STE)**
> Use the endpoint:
> 1. Put your API key in the Authorization header.
> 2. Send the request.
> 3. The response is a JSON object with the results.
