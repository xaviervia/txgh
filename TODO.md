In the Github hook

- We update the local tx configuration so that the resource name matches the branch that triggered to hook. We assume there is only one resource. This should cause tx to update the corresponding resource
- If the X-GitHub-Event	is `delete`, then we instead call the Transifex API with the name of the resource to be deleted

In the Transifex hook

- We update the Github branch to fetch using the name of the resource that was updated and use that branch for commiting the changes
