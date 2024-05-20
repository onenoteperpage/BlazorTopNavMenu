# Blazor Top Navigation Menu

This repository provides an example of how to create a top navigation menu in a Blazor project using Bootstrap 5. The default Blazor template places the navigation menu on the left side, but this example demonstrates how to move it to the top of the page.

## Table of Contents

- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Implementation](#implementation)
  - [MainLayout.razor](#mainlayoutrazor)
  - [MainLayout.razor.css](#mainlayoutrazorcss)
  - [TopNavMenu.razor](#topnavmenurazor)
  - [TopNavMenu.razor.css](#topnavmenurazorcss)
- [License](#license)

## Getting Started

To get started with this example, clone the repository and open it in your preferred C# IDE (such as Visual Studio or Visual Studio Code).

```bash
git clone https://github.com/yourusername/blazor-top-nav-menu.git
cd blazor-top-nav-menu
```

## <a name="getting-started"> Project Structure

The project contains the following key items:

- `MainLayout.razor`: The main layout file that incorporates the top navigation menu.
- `MainLayout.razor.css`: The CSS file for styling the main layout.
- `TopNavMenu.razor`: The Razor component for the top navigation menu.
- `TopNavMenu.razor.css`: _(Optional)_ The CSS file for custom styles specific to the top navigation menu.

## <a name="implementation"> Implementation

### <a name="mainlayoutrazor"> MainLayout.razor

The `MainLayout.razor` file defines the main layout of the Blazor application. It includes the TopNavMenu component and adjusts the main content accordingly.

```razor
@inherits LayoutComponentBase

<div class="page">
    <TopNavMenu />

    <main>
        <div class="top-row px-4">
            <a href="https://learn.microsoft.com/aspnet/core/" target="_blank">About</a>
        </div>

        <article class="content px-4">
            @Body
        </article>
    </main>
</div>

<div id="blazor-error-ui">
    An unhandled error has occurred.
    <a href="" class="reload">Reload</a>
    <a class="dismiss">🗙</a>
</div>
```

### <a name="mainlayoutrazorcss"> MainLayout.razor.css

The `MainLayout.razor.css` file contains the styles for the main layout. It adjusts the padding to account for the fixed top navigation bar.

```css
.page {
    position: relative;
    display: flex;
    flex-direction: column;
}

main {
    flex: 1;
    padding-top: 4.5rem; /* Adjust the padding to account for the fixed top nav bar */
}

.top-row {
    background-color: #f7f7f7;
    border-bottom: 1px solid #d6d5d5;
    justify-content: flex-end;
    height: 3.5rem;
    display: flex;
    align-items: center;
}

    .top-row ::deep a, .top-row ::deep .btn-link {
        white-space: nowrap;
        margin-left: 1.5rem;
        text-decoration: none;
    }

    .top-row ::deep a:hover, .top-row ::deep .btn-link:hover {
        text-decoration: underline;
    }

    .top-row ::deep a:first-child {
        overflow: hidden;
        text-overflow: ellipsis;
    }

#blazor-error-ui {
    background: lightyellow;
    bottom: 0;
    box-shadow: 0 -1px 2px rgba(0, 0, 0, 0.2);
    display: none;
    left: 0;
    padding: 0.6rem 1.25rem 0.7rem 1.25rem;
    position: fixed;
    width: 100%;
    z-index: 1000;
}

    #blazor-error-ui .dismiss {
        cursor: pointer;
        position: absolute;
        right: 0.75rem;
        top: 0.5rem;
    }
```

### <a name="topnavmenurazo"> TopNavMenu.razor

The `TopNavMenu.razor` file defines the top navigation menu using Bootstrap classes for styling.

```razor
<nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">BlazingTopMenu</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
            <ul class="navbar-nav me-auto mb-2 mb-md-0">
                <li class="nav-item">
                    <NavLink class="nav-link active" href="" Match="NavLinkMatch.All">
                        Home
                    </NavLink>
                </li>
                <li class="nav-item">
                    <NavLink class="nav-link" href="counter">
                        Counter
                    </NavLink>
                </li>
                <li class="nav-item">
                    <NavLink class="nav-link" href="weather">
                        Weather
                    </NavLink>
                </li>
            </ul>
            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>
    </div>
</nav>
```

### <a name="topnavmenurazorcs"> TopNavMenu.razor.css (Optional)

If you need custom styles for the top navigation menu, create a `TopNavMenu.razor.css` file and include your styles there. For basic usage, the Bootstrap classes should be sufficient.

```css
/* Example custom styles for the top navigation menu */
.navbar-brand {
    font-size: 1.25rem;
}

.nav-item {
    font-size: 1rem;
}
```

## <a name="license"> License

This project is licensed under the GPLv3 License. See the [LICENSE](/LICENSE) file for more details.