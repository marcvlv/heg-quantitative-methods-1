# Rules for the study documents

One set of rules for every subject. A new document follows these from the start;
an existing one gets brought to them before it goes near the Discord server.

Written 25 September 2026, from the Quantitative Methods I build.

---

## 1. What a document is

One subject, one self-contained HTML file, published twice: as a GitHub Pages
site and as a Claude artifact. It carries its own CSS, its own fonts and its own
icons. **Zero external resources.** It must open from a file on a plane.

It is a set of notes with links out to Khan Academy, a worked method and a
practice engine. It is not a replacement for the course and never claims to be.

---

## 2. Structure

Follow the course's own structure exactly, including its numbering.

- Read the course page before writing anything. Read it again before each new
  week: titles and release dates change.
- **One lesson per numbered part of the course.** If the course lists seven
  videos in a week, the week has seven lessons, in that order. Do not merge two
  into one because they are short, and do not split one because it is long.
- If the course has modules, the document has modules, with the course's own
  numbering (1.1, 1.2, 2.1).
- Exercise or solution videos fold into the lesson they belong to. They are not
  lessons of their own.
- **Never write a week before it is released.** A locked week exists in the
  contents as a title and nothing else. Writing it from the syllabus means
  guessing at notation and method, which is worse than a gap.

## 3. What we take, and what we write ourselves

Take freely:

- Every method, rule, definition and procedure. A method is not ownable.
- The order of topics and the depth the course goes to.
- **Every problem type.** If the course teaches break-even with a linear cost
  function and a fixed charge, so do we. The learning is in the type.

Write ourselves, always:

- All prose. Nothing paraphrased off a slide.
- Every worked example. Same structure, same difficulty, same trap, our numbers
  and our situation.
- Every practice question, for the same reason.
- Section and lesson titles, and the names of any example companies or people.

Never on the page:

- The school, the programme, the year, the campus, the platform, a teacher.
- Dates, deadlines, exam weightings, room numbers.
- The words that give it away: slide, deck, lecturer, session, homework as a
  proper noun, the course platform's name.

**The test:** a reader cannot tell which school it came from, and cannot find a
sentence or a worked example that matches the course material.

## 4. The disclaimer

Every document carries it in the footer, and every Discord post carries it at the
bottom. Same wording across subjects:

> Student notes, not official course material. Nobody teaching the subject has
> written or checked them. Use them alongside your own notes and whatever your
> course gives you, not instead of it. Where this page and your class disagree,
> your class is right.

## 5. Writing

- **No em-dashes.** Not one, anywhere. The build fails on them.
- No editorial voice. No reassurance, no "this is easier than it looks", no
  commentary on how the reader might be feeling.
- One instruction per line. A method step says what to do and what to watch for,
  and nothing else.
- Short sentences. Many readers are not native English speakers.
- About 200 to 250 words a lesson, worked examples included. A lesson that runs
  past 350 is doing two lessons' work.
- Every division is a stacked fraction. Never a slash.
- No inline translations. A reader on a browser can translate a word themselves,
  and a page speckled with dotted underlines reads as cluttered.

## 6. The anatomy of a lesson

In this order, every time:

1. **Tag line.** Where this sits: the week or module, and the part number.
2. **Title**, ours.
3. **State**: not started, in progress, completed.
4. **The Khan resources**, as a plain list, one per row, with an icon for video,
   article or exercise. Each row opens our own page for that resource, which
   carries a link out and a completed tick.
5. **Facts**, where something needs defining rather than doing.
6. **The method**, numbered, one instruction per step, with what to watch for.
7. **A worked example**, with a short reason on every line.
8. **Watch out**: the mistakes this topic actually produces, one line each.
9. **Practice**: a start screen, the questions, a score.

Sections 5 and 8 are optional. The rest are not.

## 7. Khan Academy links

- Scrape the unit pages and resolve every link by its **exact title**, so a
  wrong title fails the build instead of shipping a dead link.
- **A fetch cannot validate a Khan URL.** Every path returns HTTP 200 with the
  same shell, including paths that do not exist. Only loading the page and
  reading its heading proves anything.
- Pick per lesson, by hand, against what that lesson teaches. A unit has many
  chapters and linking to the unit is useless.
- Aim for four to six per lesson: two to watch, one to read, two to practise.
- Where Khan covers nothing, say so in one line rather than linking to something
  approximate.
- Khan's brand is theirs. Link to them, name them, and use none of their green,
  their logo, their wordmark or their illustrations.

## 8. Design

**Layout.** A top bar, a contextual card on the left, one lesson at a time. No
whole-document tree. The card lists the lessons of the current week or module
with each one's state, and the resources of the current lesson with each one's
state and a count.

**Type.** Nothing is downloaded and nothing is embedded. Georgia ships with
macOS and with Windows and was drawn for screens, so the reading face is the same
for everyone. The interface face is whatever the reader's own system uses: San
Francisco on a Mac, Segoe UI on Windows. A serif for reading and a sans for
anything you operate is what makes a page read as a document rather than an
interface. Maths is set in the system mono.

**Colour.** Palette B from the brand kit, the Anthropic-style ground, with the
MAZEN green in it:

```
--paper #F0EEE6   --paper-light #FAF9F5   --cloud   #E8E6DC
--manilla #EBDBBC --kraft       #D4A27F   --sage    #E2E8DD
--clay  #CC785C   --clay-deep   #B8543A
--forest #1A4D2E  --moss        #3E6B4A
--slate #191919   --slate-mid   #3D3D3A   --slate-soft #6B6B63
```

Two accents that do not overlap. **Terracotta is for anything you act on**: the
button, the question you are on, the live state. **Forest is for structure**: the
bar, the mark, a definition heading, a resource to go and learn from. If a colour
says what to do it is clay; if it says where you are it is green.

Three rules that are not negotiable. Text on slate is paper, and text on clay is
paper. Never clay text on kraft or manilla. Never forest and clay in the same
sentence, or neither means anything.

**One mode.** There is no light and dark. A document does not have a theme, and
two of them is two things to keep right for no gain.

**The download is the file.** Top right of the bar, an icon and the word, linking
to the generated PDF with a download attribute. Not a print dialog.

Tokens only. The build rejects a hard-coded hex outside the token block.

**Shape and motion.** One card radius of 10px and one pill of 999px, nothing
else. Transitions at 200ms. A control is at least 44px unless the pointer is
fine, so nothing moves on a laptop: the question is the pointer, not the width.

**Rhythm.** One measure, one gutter, one vertical spacing scale shared by the
contents, the lesson and the resource pages. They should look like one document.

**Formulas** wrap between terms, never scroll. A line the reader has to drag
sideways is a bug.

**Width.** Works at 320px. No horizontal page scroll at any width. Check 1440,
1150, 1000, 768, 375 and 320.

**Print.** A4, one lesson per sheet, no navigation, no top bar, no resource
pages.

**Progress** is stored per reader in the browser, with a reset. Say plainly that
it does not follow them to another device.

## 9. Verification, before anything is published

- **Every number checked in Python.** Every discriminant, every root, every
  percentage, every answer in every question bank. Not read over, executed.
- Build assertions, not intentions: the em-dash count, the tag balance, the
  required element ids, hard-coded colour, every question bank present, no
  question orphaned by a regroup, every Khan title resolved.
- Look at the built page in a browser at several widths before calling it done.
  Read the accessibility tree rather than trusting a screenshot.
- The browser pane returns stale reads. Record a value inside the page and read
  it back on a later call rather than believing the first answer.

## 10. Discord

The class server is **heg-ibm**. Each course section has a `resources` forum.

- **One post per lesson.** Never several lessons in one post.
- Title: `<Short> | <Topic>`, at most 100 characters. `QM | Quadratic equations`.
- Tag: `Notes` for a topic sheet, `Summaries` for a full lesson.
- A post is: what it covers, three or four takeaways, the link to the lesson, a
  line pointing at the official homework, the disclaimer, a last-updated stamp.
- **2,000 characters per message, hard.** Assert it in the build.
- No tables, no LaTeX, no masked links in a message you type yourself. Formulas
  in plain text inside a code block.
- Answers to any self-check go in `||spoilers||`.
- **No dates, no deadlines, no teacher names, no rooms.** The class is split
  across about twenty groups that are not on the same week.
- The course platform may be named in a post, because everyone on that server
  has an account. It is still never named on the page.
- Pin each post. The pinned list becomes the course index.

## 11. Build and repository

- **The sources live in the repository.** Everything that produces the page:
  the kit, the course map, the lessons, the banks, the scrape. A published page
  that cannot be rebuilt is a dead end.
- One entry point that runs every step in the only correct order, and fails
  loudly at the first one that breaks.
- Edit the frame **in place**, between markers. Never regenerate it from a
  snapshot: it silently reverts whatever was changed since.
- Shared kit, per-subject content. A fix to the header or the practice engine is
  made once.
- Push as **marcvlv**. `gh` drifts to the other account and the push 403s;
  `gh auth switch -u marcvlv` fixes it.
- Publish to both targets in the same pass, so the artifact and the site never
  disagree.
