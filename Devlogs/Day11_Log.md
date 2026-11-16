# Day 11 — Profile Editing, Gender Selection & Character Asset Preparation

> **Project:** System: T-0  
> **Work area:** Expo + React Native Profile screen  
> **Device validation:** Physical iPhone using Expo Go  
> **Documentation status:** Based on the code and screenshots shared during Day 11. The complete local application source is not stored in this documentation repository, so code excerpts below are focused excerpts rather than a claim that this repository contains a buildable app.

## 1. Executive Summary

Day 11 moved the Profile screen beyond a static visual mock-up. The name-editing modal was implemented and tested; gender selection was restored in the Edit Profile flow; the character carousel was reduced to the two finalized character assets, Leonhart and Emilia, with a Coming Soon placeholder for unsupported character choices.

The user also prepared separate male and female face assets and hair variations. This is the foundation for a layered character-rendering system. Face and hair are the first customization categories planned for implementation. Clothing and other appearance options will be deferred; clothing customization is intended to be premium content later.

**Important distinction:** Face and hair files have been prepared, but they are not yet proven to align correctly or render as interchangeable layers in the app. That work remains a separate implementation and validation task.

## 2. Day 11 Results at a Glance

| Workstream | Result | Evidence / confidence |
|---|---|---|
| Edit Name modal | User can open, edit, save and cancel | Tested on iPhone; user confirmed working |
| Empty-name validation | Empty/whitespace-only names cannot be saved | User confirmed working |
| Gender choices | Male, Female, Non-binary, Transgender, Others, Prefer not to say | Present in shared ProfileScreen code |
| Character assets | Leonhart and Emilia are the two available character images | Local paths supplied by user |
| Character carousel | Two real characters; Coming Soon placeholder for unsupported choices | User reported arrows and character switching working |
| Emilia asset mapping | Added avatarEmilia to profileImages.js | Exact path confirmed by file listing and Properties screenshot |
| Face assets | Four male and four female face options visible in folders | User screenshots |
| Hair assets | Multiple male and female hair variations visible in folders | User screenshots |
| Layered rendering | Not implemented/verified yet | Explicit next phase |
| Premium clothing | Product decision recorded for later | User direction |

## 3. Edit Profile: Name and Gender

### 3.1 Name editor behaviour

The existing pencil action on NameCard opens the editor through the onEdit callback. ProfileScreen.js owns the saved name, draft name, modal visibility and save/cancel behaviour.

The user tested the flow on an iPhone and confirmed:
- The modal opens with the current name.
- The text can be changed.
- Save updates the name shown on the Profile card.
- Cancel closes without applying the draft.
- Empty or whitespace-only names are rejected.
- The Save and Cancel buttons have the intended visual styling.

The current implementation keeps the value in React component state. Persistent storage across a full app restart has **not** been implemented.

### 3.2 Relevant code excerpt — name validation and save

The following is a focused excerpt from the ProfileScreen code supplied during the session:

~~~jsx
const MAX_NAME_LENGTH = 16;

const [name, setName] = useState(PROFILE.name);
const [draftName, setDraftName] = useState(PROFILE.name);
const [isEditingName, setIsEditingName] = useState(false);

const openNameEditor = () => {
  setDraftName(name);
  setDraftGender(gender);
  setIsEditingName(true);
};

const saveName = () => {
  const trimmed = draftName.trim();
  if (!trimmed) return;

  setName(trimmed);
  // Gender-to-character selection is handled here.
  setIsEditingName(false);
};
~~~

Input validation in the modal:

~~~jsx
const canSave = name.trim().length > 0;

<TextInput
  value={name}
  onChangeText={onNameChange}
  maxLength={MAX_NAME_LENGTH}
  placeholder="Enter your name"
/>

{!canSave && (
  <Text style={styles.errorText}>Name can't be empty.</Text>
)}
~~~

**Implementation note:** The modal also supports Android back dismissal through onRequestClose, uses KeyboardAvoidingView, and keeps its action buttons visible while the modal content can scroll.

## 4. Gender Selection and Character Mapping

### 4.1 Available choices

The shared implementation defines these choices:

~~~js
const GENDER_OPTIONS = [
  'Male',
  'Female',
  'Non-binary',
  'Transgender',
  'Others',
  'Prefer not to say',
];
~~~

The product behaviour agreed during the session is:

| Selected option | Character behaviour |
|---|---|
| Male | Leonhart is the default character |
| Female | Emilia is the default character |
| Non-binary | Show the Coming Soon placeholder |
| Transgender | Show the Coming Soon placeholder |
| Others | Show the Coming Soon placeholder |
| Prefer not to say | Show the Coming Soon placeholder |

The user retains the ability to switch between available character slides using the carousel arrows. Gender selection sets the default choice; it should not permanently lock the user to one character.

### 4.2 Character image mapping

The user supplied the exact local asset listing and a Windows Properties screenshot confirming the female file name and format.

Relevant mapping:

~~~js
export const profileImages = {
  // Characters
  avatarKnight: require(
    './Characters/Male & female/Pixel Art Knight with Sword and Shield (leonhard).png'
  ),
  avatarEmilia: require(
    './Characters/Male & female/Emilia (Female).webp'
  ),
};
~~~

Exact Emilia file path:

~~~text
assets/Characters/Male & female/Emilia (Female).webp
~~~

This is the path verified from the user's local file listing. The app's working carousel after the mapping correction was reported by the user.

### 4.3 Default character selection logic

The shared ProfileScreen code includes this mapping:

~~~js
const CHARACTERS = [
  { id: 'male', image: profileImages.avatarKnight },
  { id: 'female', image: profileImages.avatarEmilia },
];

const DEFAULT_CHARACTER_ID = {
  Male: 'male',
  Female: 'female',
};
~~~

When a supported gender changes, the default character index is selected. Other choices have no matching character ID and therefore use the Coming Soon experience rather than an invented character asset.

## 5. Character Carousel Behaviour

The intended user experience is summarized below:

~~~mermaid
flowchart TD
    A[Open Edit Profile] --> B[Choose a gender option]
    B --> C[Save profile]
    C --> D{Supported character available?}
    D -->|Male| E[Leonhart is selected]
    D -->|Female| F[Emilia is selected]
    D -->|Other listed options| G[Coming Soon placeholder]
    E --> H[User can use carousel arrows]
    F --> H
    G --> H
    H --> I[Only available character slides can be viewed]
~~~

The user confirmed that the carousel arrows work and that the finalized real character set is Leonhart and Emilia. No third real character has been finalized.

## 6. Face and Hair Asset Preparation

The user moved toward a layered character approach after recognizing that a single flattened character image cannot support independent face and hair changes cleanly.

### 6.1 Folder structure shown by the user

~~~text
assets/
├── Face/
│   ├── male faces/
│   │   ├── Male face 1
│   │   ├── Male face 2
│   │   ├── Male face 3
│   │   └── Male face 4
│   └── female faces/
│       ├── Female face 1
│       ├── Female face 2
│       ├── Female face 3
│       └── Female face 4
└── Hairs/
    ├── Male hair/
    │   ├── Black Hair
    │   ├── Blue Hair
    │   ├── Purple Hair
    │   └── Red Hair
    └── Female hair/
        └── Multiple colour/style variations
~~~

The screenshots show four male face variations, four female face variations, four male hair options and five female hair images. Female hair filenames appear to be generated timestamp-style names in the screenshot; exact filenames should be inspected from PowerShell before adding static imports.

### 6.2 Planned layer composition

The next implementation should use separate transparent image layers rather than trying to recolour or erase parts of the flattened character artwork at runtime.

~~~mermaid
flowchart TB
    A[Character preview container] --> B[Base body / character base]
    B --> C[Face layer]
    C --> D[Hair layer]
    D --> E[Clothing and equipment layer — later]
    E --> F[Rendered character preview]
~~~

**Alignment requirements before coding the full selector:**
1. Face and hair assets need compatible transparent canvases.
2. Their pixel dimensions and character anchor positions must match the base artwork.
3. The images must use the same scale and alignment origin.
4. Layer order must be consistent so hair appears in front of/behind the face as intended.
5. Switching an asset must change only that layer, not move or resize the rest of the character.

The asset preparation is complete enough to begin a controlled alignment experiment, but the final fit has not yet been validated in React Native.

## 7. Product Scope Decision: Free vs Premium Customization

| Customization category | Initial availability | Current status |
|---|---|---|
| Character selection | Available characters | Working carousel |
| Face | Initial customization | Assets prepared; app integration pending |
| Hair | Initial customization | Assets prepared; app integration pending |
| Clothes | Premium in future | Artwork exists; not being implemented now |
| Weapon | Premium/coin rules in future | Existing profile menu only; customization logic pending |

The clothing artwork currently has arms and legs attached. The user intends to reserve clothing changes for premium members later. No subscription/payment implementation was performed on Day 11.

## 8. Testing and Verification

| Test | Expected result | Reported result |
|---|---|---|
| Open Edit Profile | Modal appears | Pass |
| Edit and save name | Profile name updates | Pass |
| Cancel name edit | Previous saved name remains | Pass |
| Submit empty name | Save disabled / validation shown | Pass |
| Select Male | Leonhart default | Working as reported |
| Select Female | Emilia default | Working as reported |
| Select other gender options | Coming Soon placeholder | Working as reported |
| Carousel arrows | Switch between available slides | Pass |
| Emilia image path | Female image resolves | Pass after mapping correction |
| Face layer alignment | Face fits the character base | Not tested yet |
| Hair layer alignment | Hair fits the selected face/base | Not tested yet |
| Persistent name/gender storage | Values survive app restart | Not implemented |

No automated test suite, production build, or App Store build was run as part of this session.

## 9. Known Limitations and Risks

- The name and gender values currently live in component state; persistence is still pending.
- The local application source is not included in this documentation repository, so the code snippets are documentation excerpts, not a complete source snapshot.
- The third carousel slide is a placeholder, not a finalized third character.
- Face and hair assets may have different canvas dimensions or transparent padding. Their visual size cannot be assumed to match just because the images look similar in File Explorer.
- Female hair filenames must be read exactly before writing require() statements.
- Clothing and weapon customization are intentionally deferred.

## 10. Next Development Plan

| Priority | Task | Completion condition |
|---|---|---|
| 1 | Inspect image dimensions and transparency for one male face and one male hair asset | Exact dimensions and visible bounds recorded |
| 2 | Create a single layered preview for Leonhart | Face and hair align over the base character |
| 3 | Test switching between two hair variants | Only hair changes; base and face remain fixed |
| 4 | Test switching between face variants | Only face changes; hair and base remain fixed |
| 5 | Repeat alignment process for Emilia | Female face/hair layers fit correctly |
| 6 | Build the Hair and Face selection controls | User can change the selected layer from the Profile screen |
| 7 | Add persistence after the UI behaviour is stable | Selected appearance survives app restart |

## 11. Day 11 Outcome

Day 11 delivered a working Profile editing experience and restored the two finalized character choices. It also established the next technical direction: modular character rendering with independent face and hair layers.

The most important next step is **not** to build a large customization system immediately. First prove that one face and one hair asset align perfectly on Leonhart. Once that small experiment works, expand the same approach to the remaining assets and Emilia.

**Day 11 status:** Profile editing and character switching tested on device; face and hair asset preparation completed; layered customization implementation remains upcoming.

## 12. Visual Progress Snapshot

The chart below is a qualitative status snapshot from the Day 11 evidence. It is not a percentage-completion estimate.

~~~mermaid
xychart-beta
    title "Day 11 implementation status"
    x-axis ["Name edit", "Gender flow", "Carousel", "Asset prep", "Layer fit"]
    y-axis "Status (0 = pending, 1 = prepared, 2 = tested)" 0 --> 2
    bar [2, 2, 2, 1, 0]
~~~

| Status score | Meaning |
|---:|---|
| 0 | Not implemented or not yet validated |
| 1 | Assets/preparation completed; app integration or validation remains |
| 2 | Working behaviour reported and tested on the iPhone |

This makes the remaining gap visible: the profile flows are working, while asset alignment and layered rendering are the next technical milestone.

---
*System: T-0 — Development log*
