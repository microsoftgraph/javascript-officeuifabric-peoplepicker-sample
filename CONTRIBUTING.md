​
157
...and verifying the content. (The `checkout` command updates the files in `C:\Users\<yourusername>\microsoft-graph-docs` to the current state of the X2 branch.) Once you check out the new branch, you can make updates to the content and commit them as usual. However, to avoid working in the merged branch (X) by mistake, it's best to delete it (see the following **Delete a branch** section).
158
​
159
#### Delete a branch
160
​
161
Once your changes are successfully merged into the main repository, delete the branch you used because you no longer need it.  Any additional work should be done in a new branch.  
162
​
163
#### To delete a branch
164
​
165
1.  In the Git Bash command prompt, type `git checkout master`. This ensures that you aren't in the branch to be deleted (which isn't allowed).
166
2.  Next, at the command prompt, type `git branch -d <branch name>`. This deletes the branch on your computer only if it has been successfully merged to the upstream repository. (You can override this behavior with the `–D` flag, but first be sure you want to do this.)
167
3.  Finally, type `git push origin :<branch name>` at the command prompt (a space before the colon and no space after it).  This will delete the branch on your github fork.  
168
​
169
Congratulations, you have successfully contributed to the project!
170
​
171
## How to use Markdown to format your topic
172
​
173
### Article template
174
​
175
The [markdown template](/articles/0-markdown-template-for-new-articles.md) contains the basic Markdown for a topic that includes a table of contents, sections with subheadings, links to other Office developer topics, links to other sites, bold text, italic text, numbered and bulleted lists, code snippets, and images. 
176
​
177
​
178
### Standard Markdown
179
​
180
All of the articles in this repository use Markdown. A complete introduction (and listing of all the syntax) can be found at [Markdown Home] [].
181
 
182
## FAQ
183
​
184
### How do I get a GitHub account?
185
​
186
Fill out the form at [Join GitHub](https://github.com/join) to open a free GitHub account. 
187
​
188
### Where do I get a Contributor's License Agreement? 
189
​
190
You will automatically be sent a notice that you need to sign the Contributor's License Agreement (CLA) if your pull request requires one. 
191
​
192
As a community member, **you must sign the Contribution License Agreement (CLA) before you can contribute large submissions to this project**. You only need complete and submit the documentation once. Carefully review the document. You may be required to have your employer sign the document.
193
​
194
### What happens with my contributions?
195
​
196
When you submit your changes, via a pull request, our team will be notified and will review your pull request. You will receive notifications about your pull request from GitHub; you may also be notified by someone from our team if we need more information. We reserve the right to edit your submission for legal, style, clarity, or other issues.
197
 
198
### Can I become an approver for this repository's GitHub pull requests?
199
​
200
Currently, we are not allowing external contributors to approve pull requests in this repository.
201
​
202
### How soon will I get a response about my change request or issue?
203
​
204
We typically review pull requests and respond to issues within 10 business days.
205
​
206
## More resources
207
​
208
* To learn more about Markdown, go to the Git creator's site [Daring Fireball].
209
* To learn more about using Git and GitHub, first check out the [GitHub Help section] [GitHub Help].
210
​
211
[GitHub Home]: http://github.com
212
[GitHub Help]: http://help.github.com/
213
[Set Up Git]: http://help.github.com/win-set-up-git/
214
[Markdown Home]: http://daringfireball.net/projects/markdown/
215
[Daring Fireball]: http://daringfireball.net/
216
