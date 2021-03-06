- New documents don't flow to CLOSED matters
- CLOSED matters will be resynced when REOPENED
- Renaming - as we talked, blindly renames in all matters, no matter syncing status
- Syncing can happen when
  - New documents are added
  - Matter getting reopened (resulting in possible new documents being added)

### SYNCING process

1. New documents are added to a matter
2. Create a temporary list of matters that needs these new docs added
3. Find all matters to add this new document to
  - All matters in two-way family
  - All matters that are one way synced with the original matter
4. For all matters found in `3` above, filter **out** matters that
  - Is closed
  - Already have all the documents from `1`
  - Is already added to `2`
5. For EACH matters that are left after filtering in `4`
  1. Add them to the list at `2`
  2. Restart the process at `1`

### Different approach

#### Pull
- Given a matter, **pull** documents into this matter from
  - Matters in 2-way family
    - For each matter in family, pull cited/uncited
    - Dedup the list
    - Add them to the matter
  - One way synced matters
  - deletedArt will NOT flow anywhere
- Only the given matter is updated

    

