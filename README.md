
# Git Assignment - <FredyLRincon>

a. What is an issue?
An issue is a method to track bugs, enhancements, or other tasks for a project.

b. What is a pull request?
A pull request allows Git users to review proposed changes and discuss them before merging from one branch to another. Users can also comment, participate in the discussion, and contribute commits to the pull request.

c. How do I open up a pull request?
Once you have created a new repository or fork an existing one, you must clone it to your computer, create branch(es), and make and commit your changes.

git add . 

git commit -m "Describe what the change is about and why you are making this change."

push branch and changes to your GitHub repo.

git push origin git_assignment

On GitHub, click Pull Requests.

Click the New pull request button. 

You see a compare changes window.

Select the branches to compare.

Once you have selected the correct branches, you will see commits, files changed, and contributors.

Once you see the changes you want to merge, click Create Pull Request.

d. Give me a step-by-step guide on how to add someone to your repository.

In GitHub and as per Simeon's video, it is simple:

In the repository, go to Settings, Collaborators; if prompted, enter your password, click the Add People button, search for the user you want to add and click Add. 

As per Simeon's video, this method is unsuitable for adding hundreds of users in bulk, so he recommends using a GitHub rest API script. 

Having compiled the user list in an Excel spreadsheet or a CSV file, the script uses a loop that calls the GitHub API and adds each user of the TXT, CSV or spreadsheet to the repository.

for username in $(cat github_user_list.txt); do
    gh API --method PUT "repos/simeon_demo/DSI_C3_gitplayground/collaborators/$username
done

Then run the script by typing bash add_collaborators.sh

e. What is the difference between Git and GitHub?

Git is a text-based tool for developers to track and manage changes in their code. It is local, or in other words, all changes are saved on their computers.

GitHub is a GUI - a web-based service for Git repositories that allows developers to collaborate.

f. What does git diff do?

Git diff is a command highlighting the differences between two file versions.

g. What is the main branch?

It is the default branch for a git repository - the master copy. Once the branches' changes are OK, they can be incorporated into the main branch/master copy.

h. Besides our initial commit, if it is a new repository, should we push our changes directly into the main branch?

As per question g, it's not a best practice to publish directly into the master copy (main), especially when working in teams. Instead, it is better to have your drafts in a branch. Once they reach a final or ideal state, they can be published in the main branch via pull request.
  