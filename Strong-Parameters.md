    - Include a link to your Google Sheet in your Pull Request.

<br>

## Question 9

Describe Rails Strong Parameters.
Basically is declaring in private methods in a specific controller
the goal of it is to encapsulate and reuse the methods in the needed places which is permitting list of params in between create and update.


For Example:

private
    def person_params
      params.require(:person).permit(:name, :age)
    end

