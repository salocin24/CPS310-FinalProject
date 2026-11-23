# Checkpoint 1 Reflection

## 1. Which three features did you select?
- **Recipe Management:** Search by Ingredient
- **Meal Planning:** Random Meal Suggestion
- **Grocery / Calculations:** Scale Recipes by Servings

## 2. Why did you select them?
I chose features that build naturally on the existing starter code. Search by Ingredient follows the same pattern as the existing `search_by_name` function, Random Meal Suggestion is a simple, useful addition to the menu, and Scale Recipes by Servings works well because ingredient quantities are already stored as numbers in `recipes.json`.

## 3. Which feature has been most difficult so far?
Search by Ingredient, because each recipe has a nested list of ingredients, so the function needs a loop inside a loop plus a `break` so a recipe with more than one matching ingredient isn't added twice.

## 4. Which GitHub Issues represent your planned work?
- #1 Add Search by Ingredient feature (closed)
- #2 Add Random Meal Suggestion feature (closed)
- #3 Add Scale Recipes by Servings feature (open, planned for final submission)
- #4 Update README for new features
- #5 Write Checkpoint 1 reflection

## 5. Which branch or pull request best represents your development process?
PR #6 (`feature/search-by-ingredient`). The work started from Issue #1, was built on its own branch over three commits (function, tests, menu option), was tested with pytest and by hand, and was merged with "Closes #1" to link it back to the Issue.

## 6. Describe one meaningful commit and what changed.
Commit `d37cb12`, "Added tests for the search_by_ingredient() function (#1)". This commit added pytest coverage for the new feature, using a `sample_recipes` fixture for reusable test data and `@pytest.mark.parametrize` to check exact, partial, and case-insensitive matches in one test. It also added a test confirming that a search with no matches returns an empty list.

## 7. Which tests did you add?
- `test_search_by_ingredient_finds_matches`: parametrized; covers exact, partial, and case-insensitive matches
- `test_search_by_ingredient_returns_empty_list_when_no_match`
- `test_random_recipe_returns_recipe_from_list`
- `test_random_recipe_returns_none_for_empty_list`
- `test_random_recipe_returns_only_recipe_in_single_item_list`

I also added a GitHub Actions workflow (PR #8) that runs the full test suite automatically on every pull request.

## 8. Describe one bug or mistake you caught during testing.
During testing, I wrote Random.choice(recipes) instead of random.choice(recipes) in random_recipe(). Python is case-sensitive, so pytest failed with NameError: name 'Random' is not defined. Fixing the capitalization made all tests pass

## 9. What part of the current code would you improve?
The menu in `app.py` is a long if/elif chain, and every new feature means renumbering the options. A dictionary that maps choices to functions would make adding features easier.

## 10. What is your plan for the remaining work?
- Implement Scale Recipes by Servings (Issue #3) on its own branch, with tests for scaling up, scaling down, leaving the original recipe unchanged, and rejecting invalid servings
- Add Docker support for running the app and tests?
- Continue using Issues, feature branches, and PRs with CI checks for all remaining work
- Review security/privacy and AI-assisted development practices for the final reflection
- Keep the README current as features are added